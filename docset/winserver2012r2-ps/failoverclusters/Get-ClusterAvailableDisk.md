---
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
online version: 
schema: 2.0.0
title: Get-ClusterAvailableDisk
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
ms.assetid: 837E6F97-3782-4170-9DC9-0D69619DD4AA
---

# Get-ClusterAvailableDisk

## SYNOPSIS
Gets information about the disks that can support Failover Clustering and are visible to all nodes, but are not yet part of the set of clustered disks.

## SYNTAX

```
Get-ClusterAvailableDisk [[-Cluster] <String>] [-Disk <CimInstance>] [-InputObject <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-ClusterAvailableDisk** cmdlet gets information about the disks that can support Failover Clustering and are visible to all nodes, but are not yet part of the set of clustered disks.

If a disk is unexpectedly missing from the list of disks that are available for use in the cluster, then make sure that the configuration of the storage allows the operating system on all clustered servers to recognize and mount the disk as needed.
The disk must be a basic disk, not a dynamic disk, and should not be exposed to any other servers.

## EXAMPLES

### Example 1
```
PS C:\>Get-ClusterAvailableDisk
Cluster     : cluster1 
Id          : 2654136007 
Name        : Cluster Disk 4 
Number      : 7 
ScsiAddress : 50331651 
Size        : 2097152000 
Partitions  : {\\?\GLOBALROOT\Device\Harddisk7\Partition1\} 
 
Cluster     : cluster1 
Id          : 2654136015 
Name        : Cluster Disk 5 
Number      : 9 
ScsiAddress : 67108867 
Size        : 2097152000 
Partitions  : {\\?\GLOBALROOT\Device\Harddisk9\Partition1\}
```

This example lists the disks that are ready to be added to the cluster.

### Example 2
```
PS C:\>Get-ClusterAvailableDisk | Add-ClusterDisk
Name                State               Group               ResourceType 
----                -----               -----               ------------ 
Cluster Disk 4      OnlinePending       Available Storage   Physical Disk 
Cluster Disk 5      OnlinePending       Available Storage   Physical Disk
```

This example adds all disks that are ready to be added to the local cluster.

## PARAMETERS

### -Cluster
Specifies the name of the cluster on which to run this cmdlet.
If the input for this parameter is `.` or it is omitted, then the cmdlet runs on the local cluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Disk
Specifies the disks on which to enumerate.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster on which to enumerate available shared disks.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterDiskInfo

## NOTES

## RELATED LINKS

[Add-ClusterDisk](./Add-ClusterDisk.md)

