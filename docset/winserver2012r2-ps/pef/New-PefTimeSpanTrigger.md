---
external help file: Microsoft.Protocols.Tools.PowerShell.dll-Help.xml
Module Name: PEF
online version: 
schema: 2.0.0
title: New-PefTimeSpanTrigger
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 25222180-5B21-4287-9853-31C1EE56636D
ms.author: v-kaunu
ms.reviewer: brianlic
---

# New-PefTimeSpanTrigger

## SYNOPSIS
Creates a trigger that signals after the specified time span.

## SYNTAX

```
New-PefTimeSpanTrigger [-TimeSpan] <TimeSpan> [-Repeat] [<CommonParameters>]
```

## DESCRIPTION
The **New-PefTimeSpanTrigger** cmdlet creates a trigger that signals after a specified time span.
You can use a timer trigger to start or stop a Protocol Engineering Framework (PEF) Trace Session after a specified time interval elapses.
The trigger becomes active when you associate it to a PEF action.

## EXAMPLES

### Example 1: Add a Trace Filter by using a time span trigger
```
PS C:\> $TraceSession01 = New-PefTraceSession -Mode Circular
PS C:\> $Trigger01 = New-PefTimeSpanTrigger -TimeSpan (New-TimeSpan -Seconds 150)
PS C:\> Set-PefTraceFilter -PEFSession $TraceSession01 -Filter "icmp" -Trigger $Trigger01
PS C:\> Add-PefMessageSource -Session $TraceSession01 -Source "Microsoft-Pef-WFP-MessageProvider"
PS C:\> Start-PefTraceSession -PEFSession $TraceSession01
```

This example adds a Trace Filter to a Trace Session after a period of 150 seconds expires.

The first command uses the New-PefTraceSession cmdlet to create a PEF Trace Session object and stores it in the **$TraceSession01** variable.

The second command uses the current cmdlet to create a trigger with a **TimeSpan** value of 150 seconds.
The command stores the trigger in the **$Trigger01** variable.
To specify the **TimeSpan** value, type `Get-Help New-TimeSpan` to learn how to use the **New-TimeSpan** cmdlet.

The third command uses the Set-PefTraceFilter to set a Trace Filter with the string value "icmp" for the Trace Session object that is stored in the **$TraceSession01** variable.
This command specifies the trigger stored in the **$Trigger01** variable, which causes the specified Trace Filter to be applied to the Trace Session message retrieval action 150 seconds after the session starts.

The fourth command uses the Add-PefMessageSource cmdlet to specify a message provider for the Trace Session object stored in the **$TraceSession01** variable.

The final command uses the Start-PefTraceSession cmdlet to start the Trace Session stored in the **$TraceSession01** variable.

## PARAMETERS

### -Repeat
Indicates that the trigger runs on each occurrence of a time-span interval that you specify.
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

### -TimeSpan
Specifies the amount of time before the server fires the trigger.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

[New-PefTraceSession](./New-PefTraceSession.md)

[Set-PefTraceFilter](./Set-PefTraceFilter.md)

[Add-PefMessageSource](./Add-PefMessageSource.md)

[Stop-PefTraceSession](./Stop-PefTraceSession.md)

[Start-PefTraceSession](./Start-PefTraceSession.md)

