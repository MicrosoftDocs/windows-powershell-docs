---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-ClusterNetworkInterface
ms.reviewer:
ms.assetid: 923D1109-52BC-4002-BDEC-727597CE3585
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
The **Get-ClusterNetworkInterface** cmdlet gets information about one or more network adapters in a failover cluster.
A failover cluster requires network connectivity among nodes and between clients and nodes.

## EXAMPLES

### Example 1
```
PS C:\> Get-ClusterNetworkInterface
Name                Node                Network                           State 
----                ----                -------                           ----- 
node1 - Local A ...  node1               Cluster Network 1                    Up 
node2 - Local A ...  node2               Cluster Network 1                    Up 
node1 - Local A ...  node1               Cluster Network 2                    Up 
node2 - Local A ...  node2               Cluster Network 2                    Up
```

This example displays information about the physical network adapters used by the local cluster.

### Example 2
```
PS C:\> Get-ClusterNode -Name node1 | Get-ClusterNetworkInterface
Name                Node                Network                           State 
----                ----                -------                           ----- 
node1 - Local A ...  node1               Cluster Network 1                    Up 
node1 - Local A ...  node1               Cluster Network 2                    Up
```

This example displays information about the physical network adapters used by node1 in the local cluster.
This cmdlet is equivalent to `Get-ClusterNetworkInterface -Node node1`.

## PARAMETERS

### -Cluster
Specifies the name of the cluster on which to run this cmdlet.
If the input for this parameter is `.` or it is omitted, then the cmdlet runs on the local cluster.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

### Microsoft.FailoverClusters.PowerShell.ClusterNetwork

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterNetworkInterface

## NOTES

## RELATED LINKS

[Get-ClusterNetwork](./Get-ClusterNetwork.md)

