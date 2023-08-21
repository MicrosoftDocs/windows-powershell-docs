---
external help file: ScheduledTask_Cmdlets.xml
Module Name: ScheduledTasks
online version: https://learn.microsoft.com/powershell/module/scheduledtasks/new-scheduledtasktrigger?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-ScheduledTaskTrigger

## SYNOPSIS
Creates a scheduled task trigger object.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-ScheduledTaskTrigger [-Once] [-RandomDelay <TimeSpan>] [-RepetitionDuration <TimeSpan>]
 [-RepetitionInterval <TimeSpan>] -At <DateTime>
```

### UNNAMED_PARAMETER_SET_2
```
New-ScheduledTaskTrigger [-Daily] [-DaysInterval <Int32>] [-RandomDelay <TimeSpan>] -At <DateTime>
```

### UNNAMED_PARAMETER_SET_3
```
New-ScheduledTaskTrigger [-Weekly] [-RandomDelay <TimeSpan>] [-WeeksInterval <Int32>] -At <DateTime>
 -DaysOfWeek <DayOfWeek[]>
```

### UNNAMED_PARAMETER_SET_4
```
New-ScheduledTaskTrigger [-AtLogOn] [-RandomDelay <TimeSpan>] [-User <String>]
```

### UNNAMED_PARAMETER_SET_5
```
New-ScheduledTaskTrigger [-AtStartup] [-RandomDelay <TimeSpan>]
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

### -At
Specifies a date and time to trigger the task.
This parameter is valid for calendar-based triggers (Once, Daily, Weekly).

```yaml
Type: DateTime
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
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
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AtStartup
Indicates that a trigger starts a task when the system is started.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Daily
Indicates that a trigger starts a task on a recurring daily schedule.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysInterval
Specifies the interval between the days in the schedule.
An interval of 1 produces a daily schedule.
An interval of 2 produces an every-other day schedule.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: { DayOfWeek.Monday, DayOfWeek.Tuesday, DayOfWeek.Wednesday, DayOfWeek.Thursday, DayOfWeek.Friday, DayOfWeek.Saturday, DayOfWeek.Sunday }
Accept pipeline input: False
Accept wildcard characters: True
```

### -Once
Indicates that a trigger starts a task once at a time specified in the **At** parameter.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
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
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -RepetitionDuration
Specifies how long the repetition pattern repeats after the task starts.

```yaml
Type: TimeSpan
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
This cycle continues for the time that you specify for the **RepetitionDuration** parameter.

```yaml
Type: TimeSpan
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Weekly
Indicates that the trigger starts a task on a recurring weekly schedule.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WeeksInterval
Specifies the interval between the weeks in the schedule.
An interval of 1 produces a weekly schedule.
An interval of 2 produces an every-other week schedule.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_TaskTrigger

## NOTES

## RELATED LINKS

[New-ScheduledTaskAction](./New-ScheduledTaskAction.md)

[New-ScheduledTask](./New-ScheduledTask.md)

[Get-ScheduledTaskInfo](./Get-ScheduledTaskInfo.md)

[Enable-ScheduledTask](./Enable-ScheduledTask.md)

[Register-ScheduledTask](./Register-ScheduledTask.md)

[Register-ScheduledTask](./Register-ScheduledTask.md)

[Start-ScheduledTask](./Start-ScheduledTask.md)

