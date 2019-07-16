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
title: Add-ClusterDisk
ms.reviewer:
ms.assetid: CB1E7D0E-5EC6-45DA-81BF-53CEBED5D827
---

# Add-ClusterDisk

## SYNOPSIS
Makes a new disk available for use in a failover cluster.

## SYNTAX

```
Add-ClusterDisk [-InputObject] <PSObject[]> [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-ClusterDisk** cmdlet makes a new disk available for use in a failover cluster.
The disk (LUN) must be exposed to all nodes in the failover cluster, and should not be exposed to any other servers.

When adding a disk, make sure that the configuration of the storage allows the operating system to recognize and mount the disk as needed.
The disk must be a basic disk, not a dynamic disk, and should not be exposed to servers outside the cluster.
The **Get-ClusterAvailableDisk** cmdlet gets information about disks that you can add to the cluster.

## EXAMPLES

### Example 1: Add available disks to the Available Storage group
```
PS C:\> Get-ClusterAvailableDisk | Add-ClusterDisk
Name                State               Group               ResourceType 
----                -----               -----               ------------ 
Cluster Disk 7      OnlinePending       Available Storage   Physical Disk 
Cluster Disk 8      OnlinePending       Available Storage   Physical Disk
```

This example identifies the disks that are ready to be added to the cluster, and then adds them to Available Storage cluster group.

### Example 2: Add a specific available disk to Available Storage
```
PS C:\> Get-ClusterAvailableDisk | Where-Object -FilterScript { $_.ScsiAddress -Eq 50331651 } | Add-ClusterDisk
Name                State               Group               ResourceType 
----                -----               -----               ------------ 
Cluster Disk 4      OnlinePending       Available Storage   Physical Disk
```

This example examines disks that are ready to be added to the cluster, finds the disk with a specific SCSI address, and adds it to Available Storage cluster group.

### Example 3: Cluster a physical disk
```
PS C:\> Get-Disk -Number 11 | Add-ClusterDisk
Name                          State                         OwnerGroup                    ResourceType 
----                          -----                         ----------                    ------------ 
Cluster Disk 5                OnlinePending                 Available Storage             Physical Disk
```

This example clusters a physical disk.
This cmdlet adds a physical disk to the **Available Storage** for the cluster.

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
Specifies the list of shared disks to add to the cluster.
The list of disks is generated with the **Get-ClusterAvailableDisk** cmdlet.

```yaml
Type: PSObject[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterDiskInfo

### Microsoft.Management.Infrastructure.CimInstance
This object is output from the Get-Disk and the **Get-VirtualDisk** cmdlets.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Disk
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## NOTES

## RELATED LINKS

[Get-ClusterAvailableDisk](./Get-ClusterAvailableDisk.md)

[Test-Cluster](./Test-Cluster.md)

[Get-Disk](../storage/Get-Disk.md)

[Get-VirtualDisk](../storage/Get-VirtualDisk.md)

