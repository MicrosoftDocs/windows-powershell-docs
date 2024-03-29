---
external help file: ScheduledTask_Cmdlets.xml
Module Name: ScheduledTasks
online version: https://learn.microsoft.com/powershell/module/scheduledtasks/register-clusteredscheduledtask?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Register-ClusteredScheduledTask

## SYNOPSIS
Registers a scheduled task on a failover cluster.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Register-ClusteredScheduledTask [-TaskName] <String> [[-TaskType] <ClusterTaskTypeEnum>]
 [-Action] <CimInstance[]> [[-Trigger] <CimInstance[]>] [[-Settings] <CimInstance>] [[-Description] <String>]
 [[-Cluster] <String>] [[-Resource] <String>] [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Register-ClusteredScheduledTask [-TaskName] <String> [[-TaskType] <ClusterTaskTypeEnum>]
 [-InputObject] <CimInstance> [[-Cluster] <String>] [[-Resource] <String>] [-AsJob]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_3
```
Register-ClusteredScheduledTask [-TaskName] <String> [[-TaskType] <ClusterTaskTypeEnum>] [-Xml] <String>
 [[-Cluster] <String>] [[-Resource] <String>] [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Register-ClusteredScheduledTask** cmdlet registers a clustered scheduled task on a failover cluster.
The new task runs scheduled actions as defined by task triggers.
As specified in the **TaskType** parameter, an action runs on a resource specific node, an active failover node, or on all cluster nodes.

For more information about the Windows Server® 2012 Task Scheduler, see the Task Scheduler Overviewhttp://technet.microsoft.com/en-us/library/cc721871.aspx topic in the TechNet Library at http://technet.microsoft.com/en-us/library/cc721871.aspx.

## EXAMPLES

### Example 1: Register a task on a cluster
```
PS C:\>$Action = New-ScheduledTaskAction -Execute Calc PS C:\>$Trigger = New-ScheduledTaskTrigger -At 12:00 -Once PS C:\>Register-ClusteredScheduledTask -TaskName "CalcTask01" -TaskType ClusterWide -Action $Action -Trigger $Trigger -Cluster "Cluster01"
```

This example registers a cluster-wide task.

The first command uses the **New-ScheduledTaskAction** cmdlet to create a task action and stores that action in the $Action variable.

The second command uses the **New-ScheduledTaskTrigger** cmdlet to create a task trigger and stores that trigger in the $Trigger variable.

The final command registers a scheduled task named CalcTask01 for all cluster nodes in the cluster Cluster01.
The task uses the action and trigger stored in the two variables.

### Example 2: Register a task on the current cluster
```
PS C:\>$Action = New-ScheduledTaskAction -Execute Calc PS C:\>$Trigger = New-ScheduledTaskTrigger -At 12:00 -Once PS C:\>Register-ClusteredScheduledTask -TaskName "CalcTask02" -TaskType AnyNode -Action $Action -Trigger $Trigger
```

This example registers an active cluster nodes scheduled task.

The first command uses the **New-ScheduledTaskAction** cmdlet to create a task action and stores that action in the $Action variable.

The second command uses the **New-ScheduledTaskTrigger** cmdlet to create a task trigger and stores that trigger in the $Trigger variable.

The final command registers a scheduled task named CalcTask02 for active cluster nodes.
Because the command does not specify a cluster, it uses the current cluster.
The task uses the action and trigger stored in the two variables.

## PARAMETERS

### -Action
Specifies an array of action objects to use in the task.
To obtain a task action object, use the **New-ScheduledTaskAction** cmdlet.

A task can have a single action or up to 32 actions.
If you specify more than one action, the cluster runs them in sequence.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
Position: 4
Default value: "."
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description of a task.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.
This is a clustered scheduled task object.
To obtain a clustered scheduled task object, use the **Get-ClusteredScheduledTask** cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Resource
Specifies a cluster resource identifier.
This identifier defines a set of failover cluster nodes.
If you define a value of **ResourceSpecific** for the **TaskType** parameter, the task runs on the defined cluster nodes.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Settings
Specifies a **CimInstance** object that contains properties that Windows Task Scheduler uses to configure running of a task.
To obtain a settings object, use the **New-ScheduledTaskSettingSet** cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 5
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
Position: 1
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

Required: False
Position: 2
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
To obtain a task trigger object, use the **New-ScheduledTaskTrigger** cmdlet.

A trigger is a set of criteria that starts the running of a task.
You can use both time-based and event-based triggers.
One or more triggers can start a task.
You can specify up to 48 triggers.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 4
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
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_ClusteredScheduledTask

## NOTES

## RELATED LINKS

[New-ScheduledTaskAction](./New-ScheduledTaskAction.md)

[New-ScheduledTaskTrigger](./New-ScheduledTaskTrigger.md)

[New-ScheduledTaskSettingsSet](./New-ScheduledTaskSettingsSet.md)

[Get-ClusteredScheduledTask](./Get-ClusteredScheduledTask.md)

[Set-ClusteredScheduledTask](./Set-ClusteredScheduledTask.md)

[Unregister-ClusteredScheduledTask](./Unregister-ClusteredScheduledTask.md)

