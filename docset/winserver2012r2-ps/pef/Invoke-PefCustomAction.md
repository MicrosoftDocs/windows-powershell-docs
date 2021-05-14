---
external help file: Microsoft.Protocols.Tools.PowerShell.dll-Help.xml
Module Name: PEF
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/pef/invoke-pefcustomaction?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-PefCustomAction
---

# Invoke-PefCustomAction

## SYNOPSIS
Creates a PEF action that runs a script block.

## SYNTAX

```
Invoke-PefCustomAction [-Script] <ScriptBlock> [-Trigger <Trigger[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Invoke-PefCustomAction** cmdlet creates a Protocol Engineering Framework (PEF) action that runs a Microsoft PowerShell script block.
Specify a script block to run and a trigger for the action.

## EXAMPLES

### Example 1: Create an ICMP trigger action
```
PS C:\> $T = New-PefKeyDownTrigger -CtrlC
PS C:\> $Sb = { $Host.UI.WriteErrorLine("ICMP found") }
PS C:\> $S = New-PefTraceSession -Mode Linear -SaveOnStop -Path "C:\Traces\Simple" -Force -SaveAsParsed
PS C:\> Add-PefMessageSource -PEFSession $S -Source Microsoft-Pef-WFP-MessageProvider
PS C:\> $T2 = New-PefMessageTrigger  -PEFSession $S -Filter "ICMP" -Repeat
PS C:\> Invoke-PefCustomAction -Script $Sb -Trigger $T2
PS C:\> Stop-PefTraceSession -PEFSession $S -Trigger $T
PS C:\> Start-PefTraceSession -PEFSession $S
```

This command creates a script block, stored in the variable $Sb, that **Invoke-PefCustomAction** runs when the trigger criteria matches.
The New-PefMessageTrigger cmdlet defines the trigger by specifying a filter for ICMP.
When the trigger matches, the script block runs, which displays the message ICMP found.

## PARAMETERS

### -Script
Specifies a script block to invoke.
For more information about script blocks, type `Get-Help about_script_blocks`.

```yaml
Type: ScriptBlock
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Trigger
Specifies an array of **Trigger** objects.
When one of these triggers runs, the action runs the script block specified by the **Script** parameter.

```yaml
Type: Trigger[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-PefDateTimeTrigger](./New-PefDateTimeTrigger.md)

[New-PefKeyDownTrigger](./New-PefKeyDownTrigger.md)

[New-PefMessageTrigger](./New-PefMessageTrigger.md)

[New-PefProcessTrigger](./New-PefProcessTrigger.md)

[New-PefTimeSpanTrigger](./New-PefTimeSpanTrigger.md)

