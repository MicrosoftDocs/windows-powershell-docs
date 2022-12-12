---
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/get-hpcmetricvaluehistory?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HpcMetricValueHistory
---

# Get-HpcMetricValueHistory

## SYNOPSIS
Gets the values for a specified metric during the specified time period.

## SYNTAX

### NodeName (Default)
```
Get-HpcMetricValueHistory [-StartDate] <DateTime> [-EndDate] <DateTime> [-MetricName <String[]>]
 [-Counter <String[]>] [-NodeName <String[]>] [-Scheduler <String[]>]
 [<CommonParameters>]
```

### Node
```
Get-HpcMetricValueHistory [-StartDate] <DateTime> [-EndDate] <DateTime> [-MetricName <String[]>]
 [-Counter <String[]>] [-Node <HpcNode[]>] [-Scheduler <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcMetricValue** cmdlet gets the values for a specified metric during the specified time period.
HPC Cluster Manager uses these metrics in the heat maps for the nodes and the monitoring charts.
The time period is the period after the specified start date and time and before the specified end date and time.

You can specify the nodes for which you want to get the metric values by specifying the node name or by specifying an **HpcNode** object for the *NodeName* or *Node* parameters, respectively.

If you do not specify any metric names, the **Get-HpcMetricValueHistory** cmdlet gets the values for all of the metrics for the specified nodes, or for all of nodes in the HPC cluster if no nodes are specified.

## EXAMPLES

### Example 1: Get metric values for a day
```
PS C:\>Get-HpcMetricValueHistory -StartDate "5/18/2010 12:00:00 AM" -EndDate "5/19/2010 12:00:00 AM"
```

This command gets the values of all of the metrics for all of the nodes in an HPC cluster for the period starting at midnight on 5/18/2010 and ending at midnight on 5/19/2010.

### Example 2: Get metric values by name and date
```
PS C:\>Get-HpcMetricValueHistory -StartDate "5/18/2010 12:00:00 AM" -EndDate "5/19/2010 12:00:00 AM" -MetricName "HPCCpuUsage,HPCDiskSpace" -NodeName "ComputeNode01"
```

This command gets the values of the HPCCpuUsage and HPCDiskSpace metrics for the node named ComputeNode01 for the period starting at midnight on 5/18/2010 and ending at midnight on 5/19/2010.

### Example 3: Get metric values for a counter in a date range
```
PS C:\>Get-HpcMetricValueHistory -StartDate "5/18/2010 12:00:00 AM" -EndDate "5/18/2010 12:02:00 AM" -MetricName "HPCDiskSpace" -Counter "_Total"
```

This command gets the values of the *Total* counter for the HPCDiskSpace metric on all nodes in the HPC cluster for the period starting at midnight on 5/18/2010 and ending at 12:02 AM on 5/18/2010.

### Example 4: Get a node and get a metric value history by name
```
PS C:\>Get-HpcNode -Name "ComputeNode02" | Get-HpcMetricValueHistory -StartDate "5/18/2010 12:00:00 AM" -EndDate "5/18/2010 12:02:00 AM" -MetricName "HpcDiskQueue"
```

This command gets the **HpcNode** object for the node named ComputeNode02, and then gets the values of the HpcDiskQueue metric on that node for the period starting at midnight on 5/18/2010 and ending at 12:02 AM on 5/18/2010 by redirecting the **HpcNode** object to the input of the **Get-HpcMetricValueHistory** cmdlet.

## PARAMETERS

### -Counter
Specifies an array of counters for which you want to get the values during the date range.
A single metric can contain multiple counters.
For example, the HPCSchedulerJobs metric contains multiple job-related counters such as Total number of jobs and Number of canceled jobs.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndDate
Specifies the end date and time for the time period for which you want to get value information for the metrics.
Use the Get-Date cmdlet to get a **DateTime** object for a date and time.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MetricName
Specifies an array of names for the metrics for which you want to get the current values.
To view a list of the metrics that are available on the HPC cluster, use the Get-HpcMetric cmdlet.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Node
Specifies an array of nodes for which you want to get the values of the metrics.
Use the Get-HpcNode cmdlet to get the **HpcNode** objects for the nodes.
You cannot specify both the *Node* and *NodeName* parameters.

```yaml
Type: HpcNode[]
Parameter Sets: Node
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NodeName
Specifies an array of the names of nodes for which you want to get the values of the metrics.
You cannot specify both the *NodeName* and *Node* parameters.
This parameter is a filter parameter, so you do not receive an error for specifying a node that does not exist in the HPC cluster as long as you specify at least one node that does exist.

```yaml
Type: String[]
Parameter Sets: NodeName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that includes the metrics for which you want to get the values during the date range.
The value must be a valid computer name or IP address.
If you do not specify the *Scheduler* parameter, this cmdlet uses the scheduler on the head node that the CCP_SCHEDULER environment variable specifies.
To set this environment variable, run the following cmdlet:

`Set-Content Env:CCP_SCHEDULER \<head_node_name\>`

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartDate
Specifies the start date and time for the time period for which you want to get value information for the metrics.
Use the Get-Date cmdlet to get a **DateTime** object for a date and time.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### HpcNode[]

## OUTPUTS

### HpcMetricValueHistory[]

## NOTES
* To get the current values for metrics, use the Get-HpcMetricValue cmdlet.
* You must be a cluster administrator to run this cmdlet successfully.
* This cmdlet was introduced in HPC Pack 2008 R2. It is not supported in previous versions.

## RELATED LINKS

[Get-HpcMetric](./Get-HpcMetric.md)

[Get-HpcMetricValue](./Get-HpcMetricValue.md)

[Get-HpcNode](./Get-HpcNode.md)
