---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/get-hpcmetric?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HpcMetric
---

# Get-HpcMetric

## SYNOPSIS
Gets metrics that HPC Cluster Manager uses in the heat maps for the nodes and the monitoring charts.

## SYNTAX

```
Get-HpcMetric [[-Name] <String[]>] [-MetricTargets <MetricTarget[]>] [-Type <String[]>]
[-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcMetric** cmdlet gets the specified set of metrics that HPC Cluster Manager uses in the heat maps for the nodes and the monitoring charts.
You can specify the metrics that you want to get by any combination of the names of the metrics, the locations where the metrics are generated, and the categories for the metrics.
If you do not specify any names, locations, or categories, the **Get-HpcMetric** cmdlet gets all of the metrics for the HPC cluster.

## EXAMPLES

### Example 1: Get all metrics for the cluster
```
PS C:\>Get-HpcMetric
```

This command gets all of the metrics for the HPC cluster.

### Example 2: Get metrics by name
```
PS C:\>Get-HpcMetric -Name "HpcCpuUsage,HpcDiskSpace"
```

This command gets the metrics named HpcCpuUsage and HpcDiskSpace.

### Example 3: Get metrics by location and category
```
PS C:\>Get-HpcMetric -MetricTarget HeadNode,Cluster -Type "Performance"
```

This command gets the metrics in the performance categories that are generated on the head node or for the entire HPC cluster.

## PARAMETERS

### -Name
Specifies an array of names for the metrics that you want to get.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that includes the metrics.
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

### HpcMetric[]

## OUTPUTS

### HpcMetric[]

## NOTES
* The **Get-HpcMetric** cmdlet only gets information or **HpcMetrics** objects for the metrics, and not the values of the metrics. To get the values for the metrics, use the Get-HpcMetricValue cmdlet.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcMetricValue](./Get-HpcMetricValue.md)

[Import-HpcMetric](./Import-HpcMetric.md)

[Remove-HpcMetric](./Remove-HpcMetric.md)
