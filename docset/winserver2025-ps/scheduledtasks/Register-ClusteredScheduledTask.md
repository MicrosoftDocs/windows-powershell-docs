---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_ClusteredScheduledTask_v1.0.cdxml-help.xml
Module Name: ScheduledTasks
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/scheduledtasks/register-clusteredscheduledtask?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Register-ClusteredScheduledTask
---

# Register-ClusteredScheduledTask

## SYNOPSIS
Registers a scheduled task on a failover cluster.

## SYNTAX

### Object
```
Register-ClusteredScheduledTask [-InputObject] <CimInstance> [[-Cluster] <String>] [-TaskName] <String>
 [[-TaskType] <ClusterTaskTypeEnum>] [[-Resource] <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### Xml
```
Register-ClusteredScheduledTask [[-Cluster] <String>] [-TaskName] <String> [[-TaskType] <ClusterTaskTypeEnum>]
 [[-Resource] <String>] [-Xml] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### Params
```
Register-ClusteredScheduledTask [[-Cluster] <String>] [-TaskName] <String> [[-TaskType] <ClusterTaskTypeEnum>]
 [[-Resource] <String>] [[-Settings] <CimInstance>] [[-Description] <String>] [[-Trigger] <CimInstance[]>]
 [-Action] <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Register-ClusteredScheduledTask** cmdlet registers a clustered scheduled task on a failover cluster.
The new task runs scheduled actions as defined by task triggers.
As specified in the *TaskType* parameter, an action runs on a resource specific node, an active failover node, or on all cluster nodes.

For more information about the Task Scheduler, see the [Task Scheduler Overview](https://technet.microsoft.com/en-us/library/cc721871.aspx) topic in the TechNet Library at http://technet.microsoft.com/en-us/library/cc721871.aspx.

## EXAMPLES

### Example 1: Register a task on a cluster
```
PS C:\> $Action = New-ScheduledTaskAction -Execute Calc
PS C:\> $Trigger = New-ScheduledTaskTrigger -At 12:00 -Once
PS C:\> Register-ClusteredScheduledTask -TaskName "CalcTask01" -TaskType ClusterWide -Action $Action -Trigger $Trigger -Cluster "Cluster01"
```

This example registers a cluster-wide task.

The first command uses the New-ScheduledTaskAction cmdlet to create a task action and stores that action in the $Action variable.

The second command uses the New-ScheduledTaskTrigger cmdlet to create a task trigger and stores that trigger in the $Trigger variable.

The final command registers a scheduled task named CalcTask01 for all cluster nodes in the cluster Cluster01.
The task uses the action and trigger stored in the two variables.

### Example 2: Register a task on the current cluster
```
PS C:\> $Action = New-ScheduledTaskAction -Execute Calc
PS C:\> $Trigger = New-ScheduledTaskTrigger -At 12:00 -Once
PS C:\> Register-ClusteredScheduledTask -TaskName "CalcTask02" -TaskType AnyNode -Action $Action -Trigger $Trigger
```

This example registers an active cluster nodes scheduled task.

The first command uses the New-ScheduledTaskAction cmdlet to create a task action and stores that action in the $Action variable.

The second command uses the New-ScheduledTaskTrigger cmdlet to create a task trigger and stores that trigger in the $Trigger variable.

The final command registers a scheduled task named CalcTask02 for active cluster nodes.
Because the command does not specify a cluster, it uses the current cluster.
The task uses the action and trigger stored in the two variables.

## PARAMETERS

### -Action
Specifies an array of action objects to use in the task.
To obtain a task action object, use the New-ScheduledTaskAction cmdlet.

A task can have a single action or up to 32 actions.
If you specify more than one action, the cluster runs them in sequence.

```yaml
Type: CimInstance[]
Parameter Sets: Params
Aliases:

Required: True
Position: 2
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

### -Cluster
Specifies a name of a failover cluster.
If you do not specify a cluster, the cmdlet uses the current node cluster name.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description of a task.

```yaml
Type: String
Parameter Sets: Params
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance
Parameter Sets: Object
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Resource
Specifies a cluster resource identifier.
This identifier defines a set of failover cluster nodes.
If you define a value of ResourceSpecific for the *TaskType* parameter, the task runs on the defined cluster nodes.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Settings
Specifies a **CimInstance** object that contains properties that Windows Task Scheduler uses to configure running of a task.
To obtain a settings object, use the New-ScheduledTaskSettingsSet cmdlet.

```yaml
Type: CimInstance
Parameter Sets: Params
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TaskName
Specifies a name of a scheduled task.

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

### -TaskType
Specifies a type for the task.
The acceptable values for this parameter are:

- ResourceSpecific.
Resource specific cluster nodes.
- AnyNode.
Active cluster nodes.
- ClusterWide.
All cluster nodes.

```yaml
Type: ClusterTaskTypeEnum
Parameter Sets: (All)
Aliases:
Accepted values: ResourceSpecific, AnyNode, ClusterWide

Required: False
Position: 1
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

### -Trigger
Specifies an array of trigger objects to use in the task.
To obtain a task trigger object, use the New-ScheduledTaskTrigger cmdlet.

A trigger is a set of criteria that starts the running of a task.
You can use both time-based and event-based triggers.
One or more triggers can start a task.
You can specify up to 48 triggers.

```yaml
Type: CimInstance[]
Parameter Sets: Params
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Xml
Specifies an XML-formatted string that contains a task definition.
You can export a task definition from Task Scheduler.

The string represents the triggers, actions, and other settings for a task.
The string uses the Task Scheduler Schema.

```yaml
Type: String
Parameter Sets: Xml
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_ClusteredScheduledTask

## NOTES

## RELATED LINKS

[Get-ClusteredScheduledTask](./Get-ClusteredScheduledTask.md)

[New-ScheduledTaskAction](./New-ScheduledTaskAction.md)

[New-ScheduledTaskSettingsSet](./New-ScheduledTaskSettingsSet.md)

[New-ScheduledTaskTrigger](./New-ScheduledTaskTrigger.md)

[Set-ClusteredScheduledTask](./Set-ClusteredScheduledTask.md)

[Unregister-ClusteredScheduledTask](./Unregister-ClusteredScheduledTask.md)

