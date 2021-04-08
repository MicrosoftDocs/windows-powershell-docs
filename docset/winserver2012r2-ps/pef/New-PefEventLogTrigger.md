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
online version: https://docs.microsoft.com/powershell/module/pef/new-pefeventlogtrigger?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-PefEventLogTrigger
---

# New-PefEventLogTrigger

## SYNOPSIS
Creates a trigger that signals when an event log logs an entry.

## SYNTAX

```
New-PefEventLogTrigger [-LogName] <String> [-MachineName <String>] [-EventId <Int32>]
 [-EventSourceName <String>] [-CheckTimerPeriodMs <Int32>] [-Repeat] [<CommonParameters>]
```

## DESCRIPTION
The **New-PefEventLogTrigger** cmdlet creates a trigger that signals when a specified entry is logged in an event log.
An event log trigger waits for a specific event from the System log, Application log, or Security log.
You can monitor a remote computer or the local computer.
The trigger becomes active when you associate it to a Protocol Engineering Framework (PEF) action.

## EXAMPLES

### Example 1: Create an event log trigger that stops a trace session
```
PS C:\>$Trigger01 = New-PefEventLogTrigger -LogName "Application" -EventSourceName "PEFTestSource" -EventID 1234
PS C:\> $TraceSession01 = New-PefTraceSession -Mode Circular -Force -Path "C:\Traces\EventLog" -TotalSize 50 -SaveOnStop 
PS C:\> Add-PefMessageSource -PEFSession $TraceSession01 -Source "Microsoft-Pef-WFP-MessageProvider"
PS C:\> Stop-PefTraceSession -PEFSession $TraceSession01 -Trigger $Trigger01
PS C:\> Start-PefTraceSession -PEFSession $TraceSession01
```

This example creates an event log trigger, and then associates it to a Trace Session.
The Trace Session stops when the trigger finds the specific event in the Application log.

The first command creates a trigger object for an Application log event from the PEFTestSource source, and then stores it in the **$Trigger01** variable.

The second command uses the New-PefTraceSession cmdlet to create a Trace Session object, and then stores it in the **$TraceSession01** variable.

The third command uses the Add-PefMessageSource cmdlet to specify a provider for the session that is stored in the **$TraceSession01** variable.

The fourth command uses the Stop-PefTraceSession cmdlet to create a stop action for the event log trigger that is stored in the **$Trigger01** variable, and associates that action with the session that is stored in the **$TraceSession01** variable.

The final command uses the Start-PefTraceSession cmdlet to start the Trace Session that is stored in the **$TraceSession01** variable.

## PARAMETERS

### -CheckTimerPeriodMs
Specifies how often, in milliseconds, to check for an event.
The trigger checks whether the specified log contains the event.
The default value is 2000 ms.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EventId
Specifies the event ID of the event to wait for.
If you do not specify an ID, the trigger waits for an event with any ID.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EventSourceName
Specifies the source name of the event to wait for.
If you do not specify a name, the trigger waits for an event with any source name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogName
Specifies the name of the event log to check.
The acceptable values for this parameter are:

- Application 
- Security 
- System

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MachineName
Specifies the name of the computer to monitor for the event.
The default value is the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Repeat
Indicates that the trigger runs on each occurrence of the event.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-PefMessageSource](./Add-PefMessageSource.md)

[New-PefTraceSession](./New-PefTraceSession.md)

[New-PefWin32EventTrigger](./New-PefWin32EventTrigger.md)

[Start-PefTraceSession](./Start-PefTraceSession.md)

[Stop-PefTraceSession](./Stop-PefTraceSession.md)

