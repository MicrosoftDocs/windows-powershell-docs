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
title: Start-Cluster
ms.reviewer:
ms.assetid: A4A95DD7-4744-4BC5-8197-375971B2F599
---

# Start-Cluster

## SYNOPSIS
Starts the Cluster service on all nodes of the cluster on which it is not yet started.

## SYNTAX

```
Start-Cluster [[-Name] <String>] [-IgnorePersistentState] [-Wait <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Start-Cluster** cmdlet starts the Cluster service on all nodes of the cluster on which it is not yet started.
A node can function as part of the cluster only when the Cluster service is running on that node.

Note: This cmdlet cannot be run remotely without Credential Security Service Provider (CredSSP) authentication on the server computer.

## EXAMPLES

### Example 1
```
PS C:\> Start-Cluster
Name 
---- 
mycluster
```

This example starts all cluster nodes on the local cluster.

### Example 2
```
PS C:\> Start-Cluster -Name node2
Name 
---- 
mycluster
```

This example starts all cluster nodes on the cluster of which the node named node2 is a part.
A node name is required if all cluster nodes are stopped.
If the cluster is already running, then the cluster name, assuming the cluster name resource is online, can be used instead of the node name.

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
Specifies the time in seconds to wait for the cmdlet.
If this parameter is not specified, then the cmdlet will not return until quorum is achieved.
If the value of `0` is specified, the cmdlet will attempt to start the Cluster service on all nodes and then return without waiting.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

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

