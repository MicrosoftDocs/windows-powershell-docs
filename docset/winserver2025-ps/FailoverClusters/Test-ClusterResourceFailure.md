---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/23/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/test-clusterresourcefailure?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ClusterResourceFailure
---

# Test-ClusterResourceFailure

## SYNOPSIS
Simulates a failure of a cluster resource.

## SYNTAX

```
Test-ClusterResourceFailure [[-Name] <String>] [-InputObject <PSObject>] [-Cluster <String>]
 [<CommonParameters>]
```

## DESCRIPTION

The `Test-ClusterResourceFailure` cmdlet simulates a failure of a cluster resource.

Based on the failover and failback policies, when this cmdlet runs, the Cluster service moves the
clustered role, or resource group, and attempts to bring the clustered resource online. This cmdlet
can be used to simulate what actions the Cluster service will take when a resource fails.

## EXAMPLES

### Example 1: Simulate a failure

```powershell
Test-ClusterResourceFailure -Name "Cluster Disk 4"
```

This example simulates a failure in cluster resource named `Cluster Disk 4`.

## PARAMETERS

### -Cluster

Specifies the name of the cluster on which to run this cmdlet. If the input for this parameter is
`.` or it is omitted, then the cmdlet runs on the local cluster.

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

### -InputObject

Specifies the cluster resource of which to simulate failure.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Specifies the name of the cluster resource of which to simulate failure.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Move-ClusterGroup](./Move-ClusterGroup.md)

[Start-ClusterResource](./Start-ClusterResource.md)
