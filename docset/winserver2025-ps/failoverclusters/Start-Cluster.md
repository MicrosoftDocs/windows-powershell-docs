---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 10/21/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/start-cluster?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Cluster
---

# Start-Cluster

## SYNOPSIS
Starts the Cluster service on all nodes of the cluster on which it isn't yet started.

## SYNTAX

```
Start-Cluster [[-Name] <String>] [-IgnorePersistentState] [-Wait <Int32>] [<CommonParameters>]
```

## DESCRIPTION

The `Start-Cluster` cmdlet starts the Cluster service on all nodes of the cluster on which it isn't
yet started. A node can function as part of the cluster only when the Cluster service is running on
that node.

Note: This cmdlet cannot be run remotely without Credential Security Service Provider (CredSSP)
authentication on the server computer.

## EXAMPLES

### Example 1

```powershell
Start-Cluster
```

This example starts all cluster nodes on the local cluster.

### Example 2

```powershell
Start-Cluster -Name node2
```

This example starts all cluster nodes on the cluster of which the node named `node2` is a part. A
node name is required if all cluster nodes are stopped. If the cluster is already running, then the
cluster name, assuming the cluster name resource is online, can be used instead of the node name.

## PARAMETERS

### -IgnorePersistentState

Starts the nodes in the cluster without bringing resources online on the nodes.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: ips

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Specifies the name of the cluster to start.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cluster

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait

Specifies the time in seconds to wait for the cmdlet. If this parameter isn't specified, then the
cmdlet will not return until quorum is achieved. If the value of `0` is specified, the cmdlet will
attempt to start the Cluster service on all nodes and then return without waiting.

```yaml
Type: Int32
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

### None

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## NOTES

## RELATED LINKS

[Get-Cluster](./Get-Cluster.md)

[Get-ClusterNode](./Get-ClusterNode.md)

[New-Cluster](./New-Cluster.md)

[Remove-Cluster](./Remove-Cluster.md)

[Stop-Cluster](./Stop-Cluster.md)

[Test-Cluster](./Test-Cluster.md)
