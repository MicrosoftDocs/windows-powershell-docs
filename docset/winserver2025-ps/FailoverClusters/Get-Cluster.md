---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 02/08/2023
online version: https://learn.microsoft.com/powershell/module/failoverclusters/get-cluster?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Cluster
---

# Get-Cluster

## SYNOPSIS
Gets information about one or more failover clusters in a given domain.

## SYNTAX

```
Get-Cluster [[-Name] <String>] [-Domain <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Get-Cluster` cmdlet gets information about one or more failover clusters in a given domain.

This cmdlet can obtain a variety of configuration and state information about a failover cluster,
including the following items:

- State information about whether a backup is in progress.
- State information about whether the cluster is in a forced quorum state.
- Cross-network settings that are especially relevant for multi-site clusters.

To set a common property for the cluster, use this cmdlet to get the cluster object and then set the
appropriate property on that cluster object directly.

## EXAMPLES

### Example 1

```powershell
Get-Cluster | Format-List -Property *
```

This example displays state and property information for the local cluster in the form of a list.

### Example 2

```powershell
Get-Cluster -Name cluster1
```

This example gets information about a cluster named `cluster1`.

### Example 3

```powershell
Get-Cluster -Domain contoso.com
```

This example gets information about each of the clusters in the `contoso.com` domain.

### Example 4

```powershell
Get-Cluster | ForEach-Object -Process {$_.CrossSubnetDelay = 1500}
```

This example sets the common property called `CrossSubnetDelay` for the local cluster to `1500`.

### Example 5

```powershell
(Get-Cluster).DynamicQuorum = 1
```

This example enables the Dynamic Quorum feature for the cluster.

### Example 6

```powershell
Get-Cluster | Format-List -Property Quarantine*
```

This example shows default values for **QuarantineThreshold** and **QuarantineDuration** for the
local cluster.

- **QuarantineThreshold**: This is the number of times that a node can become isolated in an hour
 before the cluster will be quarantined. This is set to 3 by default.
- **QuarantineDuration**: This setting, set to 7200 seconds or 2 hours by default, controls how long
  a host will remain quarantined.

### Example 7

```powershell
(Get-Cluster).MaximumParallelMigrations = 2
```

Beginning with the 2022-09 Cumulative Update, you can now configure the number of parallel live
migrations within a cluster. For more information, see
[KB5017381](https://support.microsoft.com/help/5017381) for Windows Server 2022 and
[KB5017382](https://support.microsoft.com/help/5017382) for Azure Stack HCI, version 21H2.

This example sets the cluster property MaximumParallelMigrations to a value of `2`, limiting the
number of live migrations that a cluster node can participate in. Both existing and new cluster
nodes inherit this value of `2` because it's a cluster property. Setting the cluster
property overrides any values configured using the [Set-VMHost](../hyper-v/Set-VMHost.md)
command.

## PARAMETERS

### -Domain

Specifies the name of the domain in which to enumerate clusters.

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

### -Name

Specifies the name of the cluster to get.

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

### Microsoft.FailoverClusters.PowerShell.Cluster

## NOTES

## RELATED LINKS

[ForEach-Object](https://go.microsoft.com/fwlink/p/?LinkId=113300)

[Format-List](https://go.microsoft.com/fwlink/p/?LinkId=113302)

[New-Cluster](./New-Cluster.md)

[Remove-Cluster](./Remove-Cluster.md)

[Start-Cluster](./Start-Cluster.md)

[Stop-Cluster](./Stop-Cluster.md)

[Test-Cluster](./Test-Cluster.md)
