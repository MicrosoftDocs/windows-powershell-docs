---
author: Kateyanne
description: 
external help file: 
manager: dansimp
Module Name: HPC
ms.author: v-kaunu
ms.date: 12/20/2016
ms.prod: powershell
ms.reviewer: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/hpc/get-hpcclusteroverview?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HpcClusterOverview
---

# Get-HpcClusterOverview

## SYNOPSIS
Gets an overview of some metrics for the specified HPC cluster, including the number of nodes, jobs, and tasks in various states on the HPC cluster.

## SYNTAX

```
Get-HpcClusterOverview [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcClusterOverview** cmdlet gets an overview of some metrics for the specified HPC cluster, including the number of nodes, jobs, and tasks in various states on the HPC cluster.

## EXAMPLES

### Example 1: Get a cluster overview
```
PS C:\>Get-HpcClusterOverview -Scheduler "HeadNode"
```

This command gets metrics for the HPC cluster with a head node named HeadNode, including the number of nodes, jobs, and tasks in various states on the HPC cluster.

## PARAMETERS

### -Scheduler
Specifies the host name or IP address of the head node for the cluster for which you want information.
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

### ClusterOverview

## NOTES

## RELATED LINKS

[Get-HpcClusterProperty](./Get-HpcClusterProperty.md)
