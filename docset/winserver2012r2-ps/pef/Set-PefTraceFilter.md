---
author: Kateyanne
description: 
external help file: Microsoft.Protocols.Tools.PowerShell.dll-Help.xml
manager: jasgro
Module Name: PEF
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/pef/set-peftracefilter?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PefTraceFilter
---

# Set-PefTraceFilter

## SYNOPSIS
Sets a Trace Filter for a PEF Trace Session.

## SYNTAX

```
Set-PefTraceFilter [-PEFSession] <IPpkTraceSession> [[-Filter] <String>] [-Trigger <Trigger[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-PefTraceFilter** cmdlet sets a Trace Filter to a Protocol Engineering Framework (PEF) Trace Session.

## EXAMPLES

### Example 1: Add a Trace Filter to a Trace Session that closes with a stop trigger
```
PS C:\> $TraceSession01 = New-PefTraceSession -Mode Circular -Path "C:\Traces\IcmpTrace.matu" -SaveOnStop
PS C:\> $Trigger02 = New-PefTimeSpanTrigger -TimeSpan (New-TimeSpan -Seconds 150)
PS C:\> Set-PefTraceFilter -PEFSession $TraceSession01 -Filter "Icmp"
PS C:\> Add-PefMessageSource -PEFSession $TraceSession01 -Source "Microsoft-Pef-WFP-MessageProvider"
PS C:\> Stop-PefTraceSession -PEFSession $TraceSession01 -Trigger $Trigger02
PS C:\> Start-PefTraceSession -PEFSession $TraceSession01
```

This example sets a Trace Filter to a PEF Trace Session that stops after a 150 second interval expires.

The first command uses the New-PefTraceSession cmdlet to create a Trace Session object, and then stores it in the **$TraceSession01** variable.
This command includes the **SaveOnStop** parameter and specifies a file path, IcmpTrace.matu in the current directory, for the saved Trace Session.

The second command uses the New-PefTimeSpanTrigger cmdlet to create a trigger with a **TimeSpan** value of 150 seconds.
For information about how to use the **New-TimeSpan** cmdlet to specify a **TimeSpan** value, type `Get-Help New-TimeSpan`.

The third command sets a Trace Filter with the string value Icmp for the Trace Session stored in **$TraceSession01**.
Note that this filter takes effect immediately when the Trace Session starts.

The fourth command uses the Add-PefMessageSource cmdlet to specify a provider for the Trace Session stored in **$TraceSession01**.

The fifth command uses the Stop-PefTraceSession cmdlet to create a stop action for the trigger stored in the **$Trigger02** variable, and associates that action with the Trace Session stored in **$TraceSession01**.

The last command uses the Start-PefTraceSession cmdlet to start the Trace Session stored in **$TraceSession01**.

## PARAMETERS

### -Filter
Specifies a string that acts as a Trace Filter.
A Trace Filter defines the messages that a Trace Session retrieves according to the specified filtering criteria.
To learn more about Trace Filters, see Creating and Applying Trace Filtershttp://technet.microsoft.com/en-us/library/jj674813.aspx in the Message Analyzer Operating Guidehttp://technet.microsoft.com/en-us/library/jj649776.aspx.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PEFSession
Specifies an object that contains a Trace Session.
To create a Trace Session, use the New-PefTraceSession cmdlet.

```yaml
Type: IPpkTraceSession
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Trigger
Specifies an array of **Trigger** objects.

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

[Add-PefMessageSource](./Add-PefMessageSource.md)

[New-PefTraceSession](./New-PefTraceSession.md)

[New-PefDateTimeTrigger](./New-PefDateTimeTrigger.md)

[New-PefKeyDownTrigger](./New-PefKeyDownTrigger.md)

[New-PefMessageTrigger](./New-PefMessageTrigger.md)

[New-PefProcessTrigger](./New-PefProcessTrigger.md)

[New-PefTimeSpanTrigger](./New-PefTimeSpanTrigger.md)

