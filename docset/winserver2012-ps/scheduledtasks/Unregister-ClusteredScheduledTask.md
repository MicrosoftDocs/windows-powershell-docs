---
author: Kateyanne
external help file: ScheduledTask_Cmdlets.xml
manager: dansimp
Module Name: ScheduledTasks
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/scheduledtasks/unregister-clusteredscheduledtask?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Unregister-ClusteredScheduledTask

## SYNOPSIS
Removes a scheduled task from a failover cluster.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Unregister-ClusteredScheduledTask [[-InputObject] <CimInstance>] [-AsJob] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Unregister-ClusteredScheduledTask [-TaskName] <String> [[-Cluster] <String>] [-AsJob]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Unregister-ClusteredScheduledTask** cmdlet removes a clustered scheduled task from all nodes of a failover cluster.

For more information about the Windows Server® 2012 Task Scheduler, see the Task Scheduler Overviewhttp://technet.microsoft.com/en-us/library/cc721871.aspx topic in the TechNet Library at http://technet.microsoft.com/en-us/library/cc721871.aspx.

## EXAMPLES

### Example 1: Unregister a task
```
PS C:\> Unregister-ClusteredScheduledTask -TaskName "Task01" -Cluster "Cluster07"
```

This command removes the task named Task01 from the cluster named Cluster07.

## PARAMETERS

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
Specifies the name of a failover cluster.
If you do not specify a cluster, the cmdlet uses the current node cluster name.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 2
Default value: "."
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TaskName
Specifies a name of a scheduled task.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-ClusteredScheduledTask](./Get-ClusteredScheduledTask.md)

[Register-ClusteredScheduledTask](./Register-ClusteredScheduledTask.md)

[Set-ClusteredScheduledTask](./Set-ClusteredScheduledTask.md)

