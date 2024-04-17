---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/add-clusternode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-ClusterNode
---

# Add-ClusterNode

## SYNOPSIS
Adds a node (server) to a failover cluster.

## SYNTAX

```
Add-ClusterNode [[-Name] <StringCollection>] [-NoStorage] [-InputObject <PSObject>]
 [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Add-ClusterNode` cmdlet adds a node, or server, to a failover cluster. Before adding the new
node, you should run validation tests on the existing nodes together with the proposed new node.

Before adding the new node, you should run validation tests on the existing nodes together with the
proposed new node. By running the validation tests, you can confirm that the server to be added is
connected correctly to the networks and storage and that it contains the same software updates.

> [!NOTE]
> This cmdlet cannot be run remotely without Credential Security Service Provider (CredSSP)
> authentication on the server computer.

## EXAMPLES

### Example 1

```powershell
Add-ClusterNode -Name node4
```

This example adds node named `node4` to the local cluster.

### Example 2

```powershell
Get-Cluster -Name cluster1 | Add-ClusterNode -Name node3
```

This example adds the node named `node3` to cluster called `cluster1`.

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

Specifies the cluster to which to add the new cluster node.

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

Specifies the name of the cluster node to add.

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

### -NoStorage

Ensures that shared storage, on the node being joined to the cluster, will not be added to the
cluster during the join operation. Shared storage can be added by piping the ClusterDiskInfo object
from the `Get-ClusterAvailableDisk` cmdlet into the `Add-ClusterDisk` cmdlet.

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

[Add-ClusterDisk](./Add-ClusterDisk.md)

[Get-ClusterAvailableDisk](./Get-ClusterAvailableDisk.md)

[Get-ClusterNode](./Get-ClusterNode.md)

[New-Cluster](./New-Cluster.md)

[Remove-ClusterNode](./Remove-ClusterNode.md)

[Resume-ClusterNode](./Resume-ClusterNode.md)

[Start-ClusterNode](./Start-ClusterNode.md)

[Stop-ClusterNode](./Stop-ClusterNode.md)

[Suspend-ClusterNode](./Suspend-ClusterNode.md)

[Test-Cluster](./Test-Cluster.md)
