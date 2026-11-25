---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/get-clusternetworkinterface?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ClusterNetworkInterface
---

# Get-ClusterNetworkInterface

## SYNOPSIS
Gets information about one or more network adapters in a failover cluster.

## SYNTAX

```
Get-ClusterNetworkInterface [[-Name] <StringCollection>] [-Node <StringCollection>]
 [-Network <StringCollection>] [-InputObject <PSObject>] [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Get-ClusterNetworkInterface` cmdlet gets information about one or more network adapters in a
failover cluster. A failover cluster requires network connectivity among nodes and between clients
and nodes.

## EXAMPLES

### Example 1

```powershell
Get-ClusterNetworkInterface
```

This example displays information about the physical network adapters used by the local cluster.

### Example 2

```powershell
Get-ClusterNode -Name node1 | Get-ClusterNetworkInterface
```

This example displays information about the physical network adapters used by `node1` in the local
cluster. This cmdlet is equivalent to `Get-ClusterNetworkInterface -Node node1`.

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

Specifies the cluster on which to enumerate the cluster network interfaces.

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

Specifies the name of the cluster network interface to get.

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

### -Network

Specifies the name of the cluster network for which to enumerate the network interfaces.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Node

Specifies the name of the cluster node on which to enumerate the network interfaces.

```yaml
Type: StringCollection
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

### Microsoft.FailoverClusters.PowerShell.ClusterNetwork

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterNetworkInterface

## NOTES

## RELATED LINKS

[Get-ClusterNetwork](./Get-ClusterNetwork.md)
