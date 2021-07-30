---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/get-hpcmetricvalue?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HpcMetricValue
---

# Get-HpcMetricValue

## SYNOPSIS
Gets the current value of metrics that HPC Cluster Manager uses in heat maps for nodes and monitoring charts.

## SYNTAX

### Node (Default)
```
Get-HpcMetricValue [[-Name] <String[]>] [-Node <HpcNode[]>] [-MetricTargets <MetricTarget[]>]
 [-Type <String[]>] [-Counter <String[]>] [-Scheduler <String[]>] [<CommonParameters>]
```

### Nodename
```
Get-HpcMetricValue [[-Name] <String[]>] [-NodeName <String[]>] [-MetricTargets <MetricTarget[]>]
 [-Type <String[]>] [-Counter <String[]>] [-Scheduler <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcMetric** cmdlet gets the current value of the specified set of metrics for the specified nodes that HPC Cluster Manager uses in the heat maps for the nodes and the monitoring charts.

You can specify the metric values that you want to get by any combination of the names of the metrics, the locations where the metrics are generated, and the categories for the metrics.
You can specify the nodes for which you want to get the metric values by specifying the node name or an HpcNode object for the *NodeName* or *Node* parameters, respectively.

If you do not specify any names, locations, or categories, the **Get-HpcMetricValue** cmdlet gets the values of all of the metrics for the specified nodes, or for all of nodes in the HPC cluster if no nodes are specified.

## EXAMPLES

### Example 1: Get all metric values for all nodes
```
PS C:\>Get-HpcMetricValue
```

This command gets the current values of all the counters for all of the metrics on all of the nodes in the HPC cluster.

### Example 2: Get metric values by name
```
PS C:\>Get-HpcMetricValue -Name "HPCCpuUsage,HPCDiskSpace" -NodeName "ComputeNode01"
```

This command gets the current values of all of the counters for the HPCCpuUsage and HPCDiskSpace metrics for the node named ComputeNode01.

### Example 3: Get metric values for counters
```
PS C:\>Get-HpcMetricValue -Name "HpcSchedulerJobs" -Counter "Total number of jobs","Number of canceled jobs"
```

This command gets the current values of the counters named Total number of jobs and Number of canceled jobs for the metric named HpcSchedulerJobs.

### Example 4: Get all metric values for node
```
PS C:\>Get-HpcNode -Name "ComputeNode01" | Get-HpcMetricValue -MetricTarget ComputeNode
```

This command gets the current values on the compute node named ComputeNode1 for all of the counters for all of the metrics that are generated on compute nodes.

## PARAMETERS

### -Counter
Specifies an array of counters for which you want to get the current value.
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

### -Name
Specifies an array of names for the metrics for which you want to get the current values.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Node
Specifies an array of **HpcNode** objects that correspond to the nodes for which you want to get the values of the metrics.
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
Specifies an array of names of one or more nodes for which you want to get the values of the metrics.
You cannot specify both the *NodeName* and *Node* parameters.
This parameter is a filter parameter, so you do not receive an error for specifying a node the does not exist in the HPC cluster as long as you specify at least one node that does exist.

```yaml
Type: String[]
Parameter Sets: Nodename
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that includes the metrics for which you want to get the current values.
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

### -Type
Specifies an array of categories that include the metrics that you want to get.
Valid values are: Performance, Calculated.

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

### -MetricTargets
Specify an array of metric targets.
The acceptable values for this parameter are:

- Cluster
- HeadNode
- ComputeNode
- BrokerNode
- WorkStationNode
- AzureNode
- AzureBatchPool

```yaml
Type: MetricTarget[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### HpcNode[], or HpcMetric[]

## OUTPUTS

### HpcMetricValue[]

## NOTES
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcMetric](./Get-HpcMetric.md)

[Get-HpcMetricValueHistory](./Get-HpcMetricValueHistory.md)

[Get-HpcNode](./Get-HpcNode.md)
