---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-ClusterNetwork
ms.reviewer:
ms.assetid: BC7E8823-6E63-4DFB-8675-81CD5E76F4D7
---

# Get-ClusterNetwork

## SYNOPSIS
Gets information about one or more networks in a failover cluster.

## SYNTAX

```
Get-ClusterNetwork [[-Name] <StringCollection>] [-InputObject <PSObject>] [-Cluster <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-ClusterNetwork** cmdlet gets information about one or more networks in a failover cluster.
A failover cluster requires network connectivity among nodes and between clients and nodes.

## EXAMPLES

### Example 1
```
PS C:\> Get-ClusterNetwork
Name                                                                      State 
----                                                                      ----- 
Cluster Network 1                                                            Up 
Cluster Network 2                                                            Up 
Cluster Network 3                                                            Up
```

This example gets information about the networks used by the local cluster.

### Example 2
```
PS C:\> (Get-ClusterNetwork -Name "Cluster Network 1").Name = "Cluster Network 3"
```

This example renames Cluster Network 1 to Cluster Network 3.

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
Specifies the cluster on which to enumerate the cluster networks.

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
Specifies the name of the cluster network to get.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterNetwork

## NOTES

## RELATED LINKS

[Get-ClusterNetworkInterface](./Get-ClusterNetworkInterface.md)

