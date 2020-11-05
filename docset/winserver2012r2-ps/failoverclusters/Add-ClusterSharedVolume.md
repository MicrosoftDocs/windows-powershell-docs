---
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
online version: 
schema: 2.0.0
title: Add-ClusterSharedVolume
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
ms.assetid: FEE8A735-0D5F-4C07-A70E-73F0BB90DEB1
---

# Add-ClusterSharedVolume

## SYNOPSIS
Makes a volume available in Cluster Shared Volumes in a failover cluster.

## SYNTAX

```
Add-ClusterSharedVolume [[-Name] <StringCollection>] [-InputObject <PSObject>] [-Cluster <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-ClusterSharedVolume** cmdlet makes a volume available in the Cluster Shared Volumes in a failover cluster.
The Cluster Shared Volume must be chosen from the disks in Available Storage (that is, disks that have been added to the cluster but not assigned to a specific use in the cluster).

## EXAMPLES

### Example 1
```
PS C:\>Add-ClusterSharedVolume -Name "Cluster Disk 4"
Name                       State                      Node 
----                       -----                      ---- 
Cluster Disk 4             Online                     node2
```

This example adds Cluster Disk 4 to the Cluster Shared Volumes on the local cluster.

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
Specifies the cluster disk resource to be added to the Cluster Shared Volumes.

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
Specifies the name of the cluster disk resource to add.

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

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterSharedVolume

## NOTES

## RELATED LINKS

[Add-ClusterDisk](./Add-ClusterDisk.md)

[Get-ClusterSharedVolume](./Get-ClusterSharedVolume.md)

[Move-ClusterSharedVolume](./Move-ClusterSharedVolume.md)

[Remove-ClusterSharedVolume](./Remove-ClusterSharedVolume.md)

