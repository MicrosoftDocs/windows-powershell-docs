---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/get-clusternode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ClusterNode
---

# Get-ClusterNode

## SYNOPSIS
Gets information about one or more nodes, or servers, in a failover cluster.

## SYNTAX

```
Get-ClusterNode [[-Name] <StringCollection>] [-InputObject <PSObject>] [-Cluster <String>]
 <CommonParameters>]
```

## DESCRIPTION

The `Get-ClusterNode` cmdlet gets information about one or more nodes, or servers, in a failover
cluster.

Use this cmdlet to obtain information about the node status. To see the resources currently owned by
a particular node, specify that node in this cmdlet and then pipe the results through the
`Get-ClusterResource` cmdlet.

## EXAMPLES

### Example 1

```powershell
Get-ClusterNode
```

This example displays the name, id, and state of each node, or server, in the local cluster.

### Example 2

```powershell
Get-ClusterNode -Cluster cluster1
```

This example displays the name, id, and state of each node, or server, in the cluster named
`cluster1`.

### Example 3

```powershell
Get-ClusterNode -Name node1 | Get-ClusterResource
```

This example lists all cluster resources that are currently owned by node named `node1` on the local
cluster.

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

Specifies the cluster on which to enumerate cluster nodes.

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

Specifies the name of the cluster node to get.

```yaml
Type: StringCollection
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

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterNode

## NOTES

## RELATED LINKS

[Add-ClusterNode](./Add-ClusterNode.md)

[Get-ClusterResource](./Get-ClusterResource.md)

[Remove-ClusterNode](./Remove-ClusterNode.md)

[Resume-ClusterNode](./Resume-ClusterNode.md)

[Start-ClusterNode](./Start-ClusterNode.md)

[Stop-ClusterNode](./Stop-ClusterNode.md)

[Suspend-ClusterNode](./Suspend-ClusterNode.md)
