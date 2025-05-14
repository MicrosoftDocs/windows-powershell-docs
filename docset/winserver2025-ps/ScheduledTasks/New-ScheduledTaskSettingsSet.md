---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_ScheduledTask_v1.0.cdxml-help.xml
Module Name: ScheduledTasks
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/scheduledtasks/new-scheduledtasksettingsset?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-ScheduledTaskSettingsSet
---

# New-ScheduledTaskSettingsSet

## SYNOPSIS
Creates a new scheduled task settings object.

## SYNTAX

```
New-ScheduledTaskSettingsSet [-DisallowDemandStart] [-DisallowHardTerminate]
 [-Compatibility <CompatibilityEnum>] [-DeleteExpiredTaskAfter <TimeSpan>] [-AllowStartIfOnBatteries]
 [-Disable] [-MaintenanceExclusive] [-Hidden] [-RunOnlyIfIdle] [-IdleWaitTimeout <TimeSpan>]
 [-NetworkId <String>] [-NetworkName <String>] [-DisallowStartOnRemoteAppSession]
 [-MaintenancePeriod <TimeSpan>] [-MaintenanceDeadline <TimeSpan>] [-StartWhenAvailable]
 [-DontStopIfGoingOnBatteries] [-WakeToRun] [-IdleDuration <TimeSpan>] [-RestartOnIdle] [-DontStopOnIdleEnd]
 [-ExecutionTimeLimit <TimeSpan>] [-MultipleInstances <MultipleInstancesEnum>] [-Priority <Int32>]
 [-RestartCount <Int32>] [-RestartInterval <TimeSpan>] [-RunOnlyIfNetworkAvailable]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **New-ScheduledTaskSettingsSet** cmdlet creates an object that contains scheduled task settings.
Each scheduled task has one set of task settings.
Use this cmdlet to configure options to manage the behavior of the task upon completion, to manage the behavior of the task if a problem occurs, or to manage the behavior of the task if an instance of the task is already running.

You can use the scheduled task settings to register a new scheduled task or update an existing task registration.

## EXAMPLES

### Example 1: Register a scheduled task that uses default task settings
```
PS C:\>$Sta = New-ScheduledTaskAction -Execute "Cmd"

PS C:\>$STSet = New-ScheduledTaskSettingsSet

PS C:\>Register-ScheduledTask Task01 -Action $Sta -Settings $STSet

```
The first command creates a scheduled task action named Cmd and assigns the ScheduledTaskAction object to the $Sta variable.

The second command creates scheduled task settings that use the default settings and assigns the **ScheduledTaskSettings** object to the $Stset variable.

The third command registers the scheduled task Task01 to run the task action named Cmd and to use the default task settings.

This example registers a scheduled task that uses default task settings.

The first command creates a scheduled task action named Cmd and assigns the **ScheduledTaskAction** object to the $Sta variable.

### Example 2: Set the priority of a scheduled task
```
PS C:\>$Sta = New-ScheduledTaskAction -Execute "Cmd"

PS C:\>$STSet = New-ScheduledTaskSettingsSet -Priority 5

PS C:\>Register-ScheduledTask Task01 -Action $Sta -Settings $Stset

```
The first command creates a scheduled task action named Cmd and assigns the ScheduledTaskAction object to the $Sta variable.

The second command creates scheduled task settings that sets a higher priority for the scheduled task, and assigns the **ScheduledTaskSettings** object to the $Stset variable.

The third command registers the scheduled task Task01 to run the task action named Cmd and to use the task settings that have a priority setting of 5.

This example sets the priority of a scheduled task.

The first command creates a scheduled task action named Cmd and assigns the **ScheduledTaskAction** object to the $Sta variable.

### Example 3: Set restart settings for a scheduled task
```
PS C:\>$Sta = New-ScheduledTaskAction -Execute "Cmd"

PS C:\>$Stset = New-ScheduledTaskSettingsSet -RestartCount 3 -RestartInterval (New-TimeSpan -Minutes 60)

PS C:\>Register-ScheduledTask Task01 -Action $Sta -Settings $Stset

```
The first command creates a scheduled task action named Cmd and assigns the ScheduledTaskAction object to the $Sta variable.

The second command creates scheduled task settings that specify that Task Scheduler attempts three restarts of the task at sixty minute intervals. This command assigns the **ScheduledTaskSettings** object to the $Stset variable.

The third command registers the scheduled task Task01 to run the task action named Cmd and to use the task settings that the **ScheduledTaskSettings** object defines.

This example sets restart settings for a scheduled task.

The first command creates a scheduled task action named Cmd and assigns the **ScheduledTaskAction** object to the $Sta variable.

### Example 4: Set idle settings for a scheduled task
```
PS C:\>$Sta = New-ScheduledTaskAction -Execute "Cmd"

PS C:\>$Stset = New-ScheduledTaskSettingsSet -RunOnlyIfIdle -IdleDuration 00:02:00 -IdleWaitTimeout 02:30:00

PS C:\>Register-ScheduledTask Task01 -Action $Sta -Settings $Stset

```
The first command creates a scheduled task action named Cmd and assigns the ScheduledTaskAction object to the $Sta variable.

The second command creates scheduled task settings that specify that Task Scheduler runs the task only when the computer is idle for 2 minutes and waits for 2 hours and 30 minutes for an idle condition. This command assigns the **ScheduledTaskSettings** object to the $Stset variable.

The third command registers the scheduled task Task01 to run the task action named Cmd and to use the task settings that the **ScheduledTaskSettings** object defines.

This example sets idle settings for a scheduled task.

The first command creates a scheduled task action named Cmd and assigns the **ScheduledTaskAction** object to the $Sta variable.

### Example 5: Register a scheduled task that runs only when a network is available
```
PS C:\>$Sta = New-ScheduledTaskAction -Execute "Cmd"

PS C:\>$Stset = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable

PS C:\>Register-ScheduledTask Task01 -Action $Sta -Settings $Stset

```
The first command creates a scheduled task action named Cmd and assigns the ScheduledTaskAction object to the $Sta variable.

The second command creates scheduled task settings that specify that Task Scheduler runs the task only when a network is available. This command assigns the **ScheduledTaskSettings** object to the $Stset variable.

The third command registers the scheduled task Task01 to run the task action named Cmd only when a network is available.

This example registers a scheduled task that runs only when a network is available.

### Example 6: Register a scheduled task that has a time limit to complete the task
```
PS C:\>$Sta = New-ScheduledTaskAction -Execute "Cmd"

$Stset = New-ScheduledTaskSettingsSet -ExecutionTimeLimit (New-TimeSpan -Hours 1)

PS C:\>Register-ScheduledTask Task01 -Action $Sta -Settings $Stset

```
The first command creates a scheduled task action named Cmd and assigns the ScheduledTaskAction object to the $Sta variable.

The second command creates scheduled task settings that specify if the task is not finished after one hour, it is considered as failed. This command assigns the **ScheduledTaskSettings** object to the $Stset variable.

The third command registers the scheduled task Task01 to run the task action named Cmd, only then finish the task after one hour.

Without the ExecutionTimeLimit setting defined, the time limit set to it's default of three days for the Task Scheduler is allowed to complete the task. To configure the time limit, see [New-TimeSpan](/powershell/module/microsoft.powershell.utility/new-timespan).


## PARAMETERS

### -AllowStartIfOnBatteries
Indicates that Task Scheduler starts if the computer is running on battery power.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

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

### -Compatibility
Indicates which version of Task Scheduler with which a task is compatible.
The acceptable values for this parameter are:

- At
- V1
- Vista
- Win7
- Win8

```yaml
Type: CompatibilityEnum
Parameter Sets: (All)
Aliases:
Accepted values: At, V1, Vista, Win7, Win8

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeleteExpiredTaskAfter
Specifies the amount of time that Task Scheduler waits before deleting the task after it expires.

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

### -Disable
Indicates that the task is disabled.

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

### -DisallowDemandStart
Indicates that the task cannot be started by using either the Run command or the Context menu.

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

### -DisallowHardTerminate
Indicates that the task cannot be terminated by using TerminateProcess.

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

### -DisallowStartOnRemoteAppSession
Indicates that the task does not start if the task is triggered to run in a Remote Applications Integrated Locally (RAIL) session.

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

### -DontStopIfGoingOnBatteries
Indicates that the task does not stop if the computer switches to battery power.

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

### -DontStopOnIdleEnd
Indicates that Task Scheduler does not terminate the task if the idle condition ends before the task is completed.

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

### -ExecutionTimeLimit
Specifies the amount of time that Task Scheduler is allowed to complete the task.

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

### -Hidden
Indicates that the task is hidden in the Task Scheduler UI.

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

### -IdleDuration
Specifies the amount of time that the computer must be in an idle state before Task Scheduler runs the task.

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

### -IdleWaitTimeout
Specifies the amount of time that Task Scheduler waits for an idle condition to occur.

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

### -MaintenanceDeadline
Specifies the amount of time after which Task Scheduler attempts to run the task during emergency Automatic maintenance, if the task failed to complete during regular Automatic maintenance.

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

### -MaintenanceExclusive
Indicates that the task needs to run alone when it is started in maintenance mode.

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

### -MaintenancePeriod
Specifies the amount of time that the task needs to run once during regular Automatic maintenance.

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

### -MultipleInstances
Specifies the policy that defines how Task Scheduler handles multiple instances of the task. The acceptable values for this parameter are:

IgnoreNew. The new task instance is ignored.
Parallel. The new task instance starts immediately.
Queue. The new task instance starts as soon as the current instance completes.

```yaml
Type: MultipleInstancesEnum
Parameter Sets: (All)
Aliases:
Accepted values: Parallel, Queue, IgnoreNew

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkId
Specifies the ID of a network profile that Task Scheduler uses to determine if the task can run.
You must specify the ID of a network if you specify the *RunOnlyIfNetworkAvailable* parameter.

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

### -NetworkName
Specifies the name of a network profile that Task Scheduler uses to determine if the task can run.
The Task Scheduler UI uses this setting for display purposes.
Specify a network name if you specify the *RunOnlyIfNetworkAvailable* parameter.

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

### -Priority
Specifies the priority level of the task.
Priority must be an integer from 0 (highest priority) to 10 (lowest priority).
The default value is 7.

Priority levels 7 and 8 are used for background tasks.
Priority levels 4, 5, and 6 are used for interactive tasks.

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

### -RestartCount
Specifies the number of times that Task Scheduler attempts to restart the task.

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

### -RestartInterval
Specifies the amount of time that Task Scheduler attempts to restart the task.

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

### -RestartOnIdle
Indicates that Task Scheduler restarts the task when the computer cycles into an idle condition more than once.

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

### -RunOnlyIfIdle
Indicates that Task Scheduler runs the task only when the computer is idle.

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

### -RunOnlyIfNetworkAvailable
Indicates that Task Scheduler runs the task only when a network is available.
Task Scheduler uses the *NetworkID* parameter and *NetworkName* parameter that you specify in this cmdlet to determine if the network is available.

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

### -StartWhenAvailable
Indicates that Task Scheduler can start the task at any time after its scheduled time has passed.

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

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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

### -WakeToRun
Indicates that Task Scheduler wakes the computer before it runs the task.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_TaskSettings

## NOTES

## RELATED LINKS

[Enable-ScheduledTask](./Enable-ScheduledTask.md)

[Get-ScheduledTask](./Get-ScheduledTask.md)

[Get-ScheduledTaskInfo](./Get-ScheduledTaskInfo.md)

[New-ScheduledTask](./New-ScheduledTask.md)

[Register-ScheduledTask](./Register-ScheduledTask.md)

[Start-ScheduledTask](./Start-ScheduledTask.md)

[Unregister-ScheduledTask](./Unregister-ScheduledTask.md)
