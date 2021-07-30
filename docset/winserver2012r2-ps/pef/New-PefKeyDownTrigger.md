---
external help file: Microsoft.Protocols.Tools.PowerShell.dll-Help.xml
Module Name: PEF
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/pef/new-pefkeydowntrigger?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-PefKeyDownTrigger
---

# New-PefKeyDownTrigger

## SYNOPSIS
Creates a trigger that signals when a user presses a key.

## SYNTAX

```
New-PefKeyDownTrigger [-Key <Char[]>] [-Repeat] [<CommonParameters>]
```

## DESCRIPTION
The **New-PefKeyDownTrigger** cmdlet creates a trigger that signals when a user presses a specified key.
Use the **Key** parameter to specify the key to initiate a trigger.
You can use this keystroke trigger to start or stop a Protocol Engineering Framework (PEF) Trace Session.
The trigger becomes active when you associate it with a PEF action.

## EXAMPLES

### Example 1: Save the contents of a Trace Session with a key down trigger
```
PS C:\> $TraceSession01 = New-PefTraceSession -Mode Circular -SaveOnStop
PS C:\> Add-PefMessageSource -PEFSession $TraceSession01 -Source "Microsoft-Pef-WFP-MessageProvider"
PS C:\> $Trigger01 = New-PefKeyDownTrigger -Key S
PS C:\> Save-PefDataCollection -PEFSession $TraceSession01 -Path "C:\Traces\Trace01.matu" -Force -Trigger $Trigger01
PS C:\> Start-PefTraceSession -PEFSession $TraceSession01
```

This example creates a PEF Trace Session that you can save at any time by using the keyboard S key as a shortcut.

The first command uses the New-PefTraceSession cmdlet to create a Trace Session that runs in the Circular mode, and stores a Trace Session object in the **$TraceSession01** variable.

The second command uses the Add-PefMessageSource cmdlet to add the specified message trace source.

The third command uses the current cmdlet to create a trigger based on the keyboard shortcut S and stores it in the **$Trigger01** variable.

The fourth command creates a save action for the Trace Session stored in the **$TraceSession01** variable, which uses the trigger specified in the **$Trigger01** variable.
The command also specifies a name for the trace file to save.
In addition, the command uses the **Force** parameter and therefore does not prompt you before replacing an existing file.

The final command uses the Start-PefTraceSession cmdlet to start the session.

## PARAMETERS

### -Key
Specifies a key to initiate a trigger.
Note that Ctrl+C is no longer supported.

```yaml
Type: Char[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Repeat
Indicates that the trigger runs on each occurrence of the keyboard input that you specify.
If you do not specify this parameter, the trigger runs only once.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-PefProcessTrigger](./New-PefProcessTrigger.md)

[New-PefMessageTrigger](./New-PefMessageTrigger.md)

[New-PefTimeSpanTrigger](./New-PefTimeSpanTrigger.md)

[New-PefDateTimeTrigger](./New-PefDateTimeTrigger.md)

[Stop-PefTraceSession](./Stop-PefTraceSession.md)

[New-PefTraceSession](./New-PefTraceSession.md)

