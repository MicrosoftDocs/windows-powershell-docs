---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 10/21/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/set-clusterownernode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ClusterOwnerNode
---

# Set-ClusterOwnerNode

## SYNOPSIS
Specifies which nodes can own a resource in a failover cluster or specifies the order of preference
among owner nodes for a clustered role, or resource group.

## SYNTAX

```
Set-ClusterOwnerNode [-Resource <String>] [-Group <String>] -Owners <StringCollection>
 [-InputObject <PSObject>] [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Set-ClusterOwnerNode` cmdlet specifies which nodes can own a resource in a failover cluster
or specifies the order of preference among owner nodes for a clustered role, or resource group. The
settings that control the possible or preferred owners affect the way the cluster responds to the
failure of a resource or a clustered role.

## EXAMPLES

### Example 1

```powershell
Get-ClusterResource -Name "Cluster Disk 3" | Set-ClusterOwnerNode -Owners node1,node2
```

This example sets the possible owners for cluster named `Cluster Disk 3` on the local cluster to the
nodes named `node1` and `node2`.

### Example 2

```powershell
Set-ClusterOwnerNode -Group cluster12FS -Owners node3,node2
```

This example sets the preferred owners for the clustered service named `cluster12FS` to the node
named `node3` followed by the node named `node2` on the local cluster.

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

### -Group

Specifies the name of the cluster group for which owner nodes are set.

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

Specifies the cluster group or cluster resource for which to set owner nodes.

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

### -Owners

Specifies the list of owner nodes. If this is for a cluster group, then the sorted list of nodes is
the preferred owners for this cluster group. If this is for a cluster resource, then the list is for
the possible owners for this cluster resource.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Resource

Specifies the name of the cluster resource for which owner nodes are set.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-ClusterOwnerNode](./Get-ClusterOwnerNode.md)
