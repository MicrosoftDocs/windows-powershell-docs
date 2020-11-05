---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Import-HpcMetric
description:
keywords: powershell, cmdlet
ms.date: 12/20/2016
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: http://go.microsoft.com/fwlink/?LinkId=182659
schema: 2.0.0
ms.assetid: B0D29FB7-E5E3-466A-8247-05A7151F1734
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne

---

# Import-HpcMetric

## SYNOPSIS
Imports metrics from the specified XML file to create new metrics or overwrite existing metrics that HPC Cluster Manager uses in the heat maps for the nodes and the monitoring charts.

## SYNTAX

```
Import-HpcMetric [-Path] <String> [-Reset] [-Scheduler <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Import-HpcMetric** cmdlet imports metrics from the specified XML file to create new metrics or overwrite existing metrics that HPC Cluster Manager uses in the heat maps for the nodes and the monitoring charts.

## EXAMPLES

### Example 1: Import metrics
```
PS C:\>Import-HpcMetric -Path "C:\MyMetrics\MyCustomMetrics.xml"
```

This command imports metrics from the XML file located at C:\MyMetrics\MyCustomMetrics.xml and adds those metrics to the existing set of metrics for the HPC cluster.
If the MyCustomMetrics.xml file contains any metrics that already exist, the **Import-HpcMetric** cmdlet updates those metrics based on the setting in the XML file.

### Example 2: Import metrics to replace all current metrics
```
PS C:\>Import-HpcMetric -Path "C:\MyMetrics\MyCustomMetricsSet.xml" -Reset
```

Imports metrics from the XML file located at C:\MyMetrics\MyCustomMetricsSet.xml and replaces the entire existing set of metrics for the HPC cluster with the new set of metrics that the XML file contains.

## PARAMETERS

### -Path
Specifies the file name of the XML file that contains the information about the metrics that you want to import, including the full or relative path to the file if the file is not in the current directory.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Reset
Indicates the **Import-HpcMetric** cmdlet replaces the entire set of existing metrics with the metrics in the XML file from which you want to import metrics.
After you import metrics by using the *Reset* parameter, the HPC cluster will have exactly the same set of metrics that the XML file defines.
If you do not use the *Reset* parameter, the **Import-HpcMetric** cmdlet adds the new metrics in the XML file to the metrics that already exist for the HPC cluster, and updates the definition of any existing metrics that the XML file also contains.

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

### -Scheduler
Specifies the host name or IP address of the head node for the cluster to which you want to import the metrics.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES
* For information about the schema for the metrics XML file, see Windows HPC Server 2008: Operationshttps://technet.microsoft.com/en-us/library/cc947639.aspx (http://go.microsoft.com/fwlink/?LinkId=120726) in the TechNet Library.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcMetric](./Get-HpcMetric.md)

[Remove-HpcMetric](./Remove-HpcMetric.md)
