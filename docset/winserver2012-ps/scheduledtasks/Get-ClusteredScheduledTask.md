---
external help file: ScheduledTask_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 393366D5-4123-42FC-BC28-B015002280A6
manager: dansimp
---

# Get-ClusteredScheduledTask

## SYNOPSIS
Gets clustered scheduled tasks for a failover cluster.

## SYNTAX

```
Get-ClusteredScheduledTask [[-TaskName] <String>] [[-Cluster] <String>] [[-TaskType] <ClusterTaskTypeEnum>]
 [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-ClusteredScheduledTask** cmdlet gets the clustered scheduled tasks registered on a failover cluster.
You can specify task name or task type.

For more information about the Windows Server® 2012 Task Scheduler, see the Task Scheduler Overviewhttp://technet.microsoft.com/en-us/library/cc721871.aspx topic in the TechNet Library at http://technet.microsoft.com/en-us/library/cc721871.aspx.

## EXAMPLES

### Example 1: Get scheduled tasks
```
PS C:\> Get-ClusteredScheduledTask -TaskName "Task14" -Cluster "Cluster73"
```

This command gets the task named Task14 on the cluster named Cluster73.

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
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: "."
Accept pipeline input: False
Accept wildcard characters: False
```

### -TaskName
Specifies a name of a scheduled task.

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

### -TaskType
Specifies a type for the task.
The acceptable values for this parameter are:

- ResourceSpecific.
Resource specific cluster nodes
- AnyNode.
Active cluster nodes. 
- ClusterWide.
All cluster nodes.

```yaml
Type: ClusterTaskTypeEnum
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_ClusteredScheduledTask[]

## NOTES

## RELATED LINKS

[Register-ClusteredScheduledTask](./Register-ClusteredScheduledTask.md)

[Set-ClusteredScheduledTask](./Set-ClusteredScheduledTask.md)

[Unregister-ClusteredScheduledTask](./Unregister-ClusteredScheduledTask.md)

