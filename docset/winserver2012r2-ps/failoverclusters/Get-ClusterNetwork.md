---
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
online version: 
schema: 2.0.0
title: Get-ClusterNetwork
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
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

### EXAMPLE 1
```
PS C:\>Get-ClusterNetwork
Name                                                                      State 
----                                                                      ----- 
Cluster Network 1                                                            Up 
Cluster Network 2                                                            Up 
Cluster Network 3                                                            Up
```

This example gets information about the networks used by the local cluster.

### Example 2
```
PS C:\>(Get-ClusterNetwork -Name "Cluster Network 1").Name = "Cluster Network 3"
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterNetwork

## NOTES

## RELATED LINKS

[Get-ClusterNetworkInterface](./Get-ClusterNetworkInterface.md)

