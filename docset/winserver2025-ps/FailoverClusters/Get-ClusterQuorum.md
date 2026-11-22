---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/get-clusterquorum?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ClusterQuorum
---

# Get-ClusterQuorum

## SYNOPSIS
Gets information about the quorum configuration of a failover cluster.

## SYNTAX

```
Get-ClusterQuorum [[-Cluster] <String>] [-InputObject <PSObject>] [<CommonParameters>]
```

## DESCRIPTION

The `Get-ClusterQuorum` cmdlet gets information about the quorum configuration of a failover
cluster.

The quorum configuration in a failover cluster determines the number of failures that the cluster
can sustain. If an additional failure occurs, then the cluster must stop running. The relevant
failures in this context are failures of nodes or, in some cases, of a disk witness (which contains
a copy of the cluster configuration) or file share witness.

## EXAMPLES

### Example 1

```powershell
Get-ClusterQuorum
```

This example displays the quorum configuration for the local cluster.

### Example 2

```powershell
Get-ClusterQuorum -Cluster Cluster1
```

This example displays the quorum configuration for the cluster named `Cluster1`.

## PARAMETERS

### -Cluster

Specifies the name of the cluster on which to run this cmdlet. If the input for this parameter is
`.` or it is omitted, then the cmdlet runs on the local cluster.

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

### -InputObject

Specifies the cluster for which to query the quorum type.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterQuorumSettings

## NOTES

## RELATED LINKS

[Set-ClusterQuorum](./Set-ClusterQuorum.md)
