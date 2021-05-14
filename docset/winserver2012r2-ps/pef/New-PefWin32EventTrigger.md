---
external help file: Microsoft.Protocols.Tools.PowerShell.dll-Help.xml
Module Name: PEF
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/pef/new-pefwin32eventtrigger?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-PefWin32EventTrigger
---

# New-PefWin32EventTrigger

## SYNOPSIS
Creates a trigger that signals when a specified Win32 system event is raised.

## SYNTAX

```
New-PefWin32EventTrigger [-EventName] <String> [-CheckTimerPeriodMs <Int32>] [-Repeat] [<CommonParameters>]
```

## DESCRIPTION
The **New-PefWin32EventTrigger** cmdlet creates a trigger that signals when a specified Win32 system event is raised.
Use a Win32 system event object to control when to start or stop a trace, or trigger other actions, from the process that creates the event.
The trigger becomes active when you associate it with a Protocol Engineering Framework (PEF) action.

## EXAMPLES

### Example 1: Create aWin32 event trigger that stops a trace session
```
PS C:\>$Trigger01 = New-PefWin32EventTrigger -EventName "TestEvent" -CheckTimerPeriodMs 5
PS C:\> $TraceSession01 = New-PefTraceSession -Mode Linear -Force -Path "C:\traces\Win32Event" -Name "TestEventLogEventScenario" -SaveOnStop 
PS C:\> Add-PefMessageSource -PEFSession $TraceSession01 -Source "Microsoft-Pef-WFP-MessageProvider" 
PS C:\> Stop-PefTraceSession -PEFSession $TraceSession01 -Trigger $Trigger01
PS C:\> Start-PefTraceSession -PEFSession $TraceSession01
```

This example creates a Win32 system event trigger, and then associates it to a Trace Session.
The Trace Session stops when the trigger signals the named system event.

The first command creates a trigger object for a Win32 system event named TestEvent, and then stores in the **$Trigger01** variable.
The trigger checks for the event every five milliseconds.

The second command uses the New-PefTraceSession cmdlet to create a Trace Session object, and then stores it in the **$TraceSession01** variable.

The third command uses the Add-PefMessageSource cmdlet to specify a provider for the session that is stored in **$TraceSession01**.

The fourth command uses the Stop-PefTraceSession cmdlet to create a stop action for the Win32 system event trigger stored in **$Trigger01**, and associates that action with the session that is stored in **$TraceSession01**.
An external process can now signal the event to stop the trace.

The final command uses the Start-PefTraceSession cmdlet to start the session that is stored in **$TraceSession01**.

## PARAMETERS

### -CheckTimerPeriodMs
Specifies how often, in milliseconds, to check for an event.
The default value is 1000 ms.

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

### -EventName
Specifies the name of the event to wait for.

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

[New-PefEventLogTrigger](./New-PefEventLogTrigger.md)

[New-PefTraceSession](./New-PefTraceSession.md)

[Start-PefTraceSession](./Start-PefTraceSession.md)

[Stop-PefTraceSession](./Stop-PefTraceSession.md)

