---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_ScheduledTask_v1.0.cdxml-help.xml
Module Name: ScheduledTasks
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/scheduledtasks/new-scheduledtasktrigger?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-ScheduledTaskTrigger
---

# New-ScheduledTaskTrigger

## SYNOPSIS
Creates a scheduled task trigger object.

## SYNTAX

### Once (Default)
```
New-ScheduledTaskTrigger [-RandomDelay <TimeSpan>] -At <DateTime> [-Once] [-RepetitionDuration <TimeSpan>]
 [-RepetitionInterval <TimeSpan>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### Daily
```
New-ScheduledTaskTrigger [-Daily] [-DaysInterval <UInt32>] [-RandomDelay <TimeSpan>] -At <DateTime>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### Weekly
```
New-ScheduledTaskTrigger [-RandomDelay <TimeSpan>] -At <DateTime> [-DaysOfWeek <DayOfWeek[]>] [-Weekly]
 [-WeeksInterval <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### Startup
```
New-ScheduledTaskTrigger [-RandomDelay <TimeSpan>] [-AtStartup] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### Logon
```
New-ScheduledTaskTrigger [-RandomDelay <TimeSpan>] [-AtLogOn] [-User <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **New-ScheduledTaskTrigger** cmdlet creates and returns a new scheduled task trigger object.

You can use a time-based trigger or an event-based trigger to start a task.
Time-based triggers include starting a task at a specific time or starting a task multiple times on a daily or weekly schedule.
Event-based triggers include starting a task when the system starts up or when a user logs on to the computer.
Each task can contain one or more triggers, which means there are many ways that you can start a task.
If a task has multiple triggers, Task Scheduler starts the task when any of the triggers occur.

## EXAMPLES

### Example 1: Register a scheduled task that starts a task once
```
PS C:\>$Sta = New-ScheduledTaskAction -Execute "Cmd"
PS C:\>$Stt = New-ScheduledTaskTrigger -Once -At 3am
PS C:\>Register-ScheduledTask Task01 -Action $Sta -Trigger $Stt
```

This example registers a scheduled task that starts once.

The first command creates a scheduled task action named Cmd and assigns the **ScheduledTaskAction** object to the $Sta variable.
The second command creates a scheduled task trigger that starts the task once at 3:00 A.M and assigns the **ScheduledTaskTrigger** object to the $Stt variable.
The third command registers the scheduled task Task01 to run the task action named Cmd once at 3:00 A.M.

### Example 2: Register a scheduled task that starts every day
```
PS C:\>$Sta = New-ScheduledTaskAction -Execute "Cmd"
PS C:\>$Stt = New-ScheduledTaskTrigger -Daily -At 3am
PS C:\>Register-ScheduledTask Task01 -Action $Sta -Trigger $Stt
```

This example registers a scheduled task that starts every day.

The first command creates a scheduled task action named Cmd and assigns the **ScheduledTaskAction** object to the $Sta variable.
The second command creates a scheduled task trigger that starts every day at 3:00 A.M and assigns the **ScheduledTaskTrigger** object to the $Stt variable.
The third command registers the scheduled task Task01 to run the task action named Cmd every day at 3:00 A.M.

### Example 3: Register a scheduled task that starts every 3 days
```
PS C:\>$Sta = New-ScheduledTaskAction -Execute "Cmd"
PS C:\>$Stt = New-ScheduledTaskTrigger -Daily -DaysInterval 3 -At 3am
PS C:\>Register-ScheduledTask Task01 -Action $Sta -Trigger $Stt
```

This example registers a scheduled task that starts every 3 days.

The first command creates a scheduled task action named Cmd and assigns the **ScheduledTaskAction** object to the $Sta variable.
The second command creates a scheduled task trigger that starts every 3 days at 3:00 A.M and assigns the **ScheduledTaskTrigger** object to the $Stt variable.
The third command registers the scheduled task Task01 to run the task action named cmd every 3 days at 3:00 A.M.

### Example 4: Register a scheduled task that starts every-other week
```
PS C:\>$Sta = New-ScheduledTaskAction -Execute "Cmd"
PS C:\>$Stt = New-ScheduledTaskTrigger -Weekly -WeeksInterval 2 -DaysOfWeek Sunday -At 3am
PS C:\>Register-ScheduledTask Task01 -Action $Sta -Trigger $Stt
```

This example registers a scheduled task that starts every other week.

The first command creates a scheduled task action named Cmd and assigns the **ScheduledTaskAction** object to the $Sta variable.
The second command creates a scheduled task trigger that starts every other Sunday at 3:00 A.M and assigns the **ScheduledTaskTrigger** object to the $Stt variable.
The third command registers the scheduled task Task01 to run the task action named Cmd every other Sunday at 3:00 A.M.

### Example 5: Register a scheduled task that starts when a user logs on
```
PS C:\>$Sta = New-ScheduledTaskAction -Execute "Cmd"
PS C:\>$Stt = New-ScheduledTaskTrigger -AtLogon
PS C:\>Register-ScheduledTask Task01 -Action $Sta -Trigger $Stt
```

This example registers a scheduled task that starts when a user logs on.

The first command creates a scheduled task action named Cmd and assigns the **ScheduledTaskAction** object to the $Sta variable.
The second command creates a scheduled task trigger that starts when a user logs on, and assigns the **ScheduledTaskTrigger** object to the $Stt variable.
The third command registers the scheduled task Task01 to run the task action named Cmd when a user logs on.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -At
Specifies a date and time to trigger the task.
This parameter is valid for calendar-based triggers (Once, Daily, Weekly).

```yaml
Type: DateTime
Parameter Sets: Once, Daily, Weekly
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AtLogOn
Indicates that a trigger starts a task when a user logs on.

```yaml
Type: SwitchParameter
Parameter Sets: Logon
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AtStartup
Indicates that a trigger starts a task when the system is started.

```yaml
Type: SwitchParameter
Parameter Sets: Startup
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a Common Information Model (CIM) session object that represents a connection to a local computer or a remote computer, such as the output of a New-CimSession or Get-CimSession cmdlet. The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Daily
Indicates that a trigger starts a task on a recurring daily schedule.

```yaml
Type: SwitchParameter
Parameter Sets: Daily
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysInterval
Specifies the interval between the days in the schedule.
An interval of 1 produces a daily schedule.
An interval of 2 produces an every-other day schedule.

```yaml
Type: UInt32
Parameter Sets: Daily
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysOfWeek
Specifies an array of the days of the week on which Task Scheduler runs the task.

```yaml
Type: DayOfWeek[]
Parameter Sets: Weekly
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Once
Indicates that a trigger starts a task once at a time specified in the *At* parameter.

```yaml
Type: SwitchParameter
Parameter Sets: Once
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RandomDelay
Specifies a random amount of time to delay the start time of the trigger.
The delay time is a random time between the time the task triggers and the time that you specify in this setting.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RepetitionDuration
Specifies how long the repetition pattern repeats after the task starts.

```yaml
Type: TimeSpan
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RepetitionInterval
Specifies an amount of time between each restart of the task.
The task will run, wait for the time interval specified, and then run again.
This cycle continues for the time that you specify for the *RepetitionDuration* parameter.

```yaml
Type: TimeSpan
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer. The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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

### -User
Specifies the identifier of the user for a trigger that starts a task when a user logs on.

```yaml
Type: String
Parameter Sets: Logon
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Weekly
Indicates that the trigger starts a task on a recurring weekly schedule.

```yaml
Type: SwitchParameter
Parameter Sets: Weekly
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WeeksInterval
Specifies the interval between the weeks in the schedule.
An interval of 1 produces a weekly schedule.
An interval of 2 produces an every-other week schedule.

```yaml
Type: UInt32
Parameter Sets: Weekly
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_TaskTrigger

## NOTES

## RELATED LINKS

[Enable-ScheduledTask](./Enable-ScheduledTask.md)

[Get-ScheduledTaskInfo](./Get-ScheduledTaskInfo.md)

[New-ScheduledTask](./New-ScheduledTask.md)

[New-ScheduledTaskAction](./New-ScheduledTaskAction.md)

[Register-ScheduledTask](./Register-ScheduledTask.md)

[Start-ScheduledTask](./Start-ScheduledTask.md)

