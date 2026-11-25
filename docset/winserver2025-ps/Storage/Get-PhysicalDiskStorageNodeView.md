---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-physicaldiskstoragenodeview?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PhysicalDiskStorageNodeView
---

# Get-PhysicalDiskStorageNodeView

## SYNOPSIS
Gets the node view of a physical disk.

## SYNTAX

```
Get-PhysicalDiskStorageNodeView [[-StorageNode] <CimInstance>] [[-PhysicalDisk] <CimInstance>]
 [[-CimSession] <CimSession>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-PhysicalDiskStorageNodeView** cmdlet gets the node view of physical disk.
The object that this cmdlet returns includes physical disk properties such as Microsoft Multipath I/O (MPIO) settings, drive health, and so on.

You can use this cmdlet to debug disk issues specific to a node.

## EXAMPLES

### Example 1: Get the node view for a Storage node
```
PS C:\>$N = Get-StorageNode -Name "ClusterNode01"
PS C:\> $Output = Get-PhysicalDiskStorageNodeView -StorageNode $N
PS C:\> $Pd = Get-PhysicalDisk -ObjectId $Output[0].PhysicalDiskObjectId
```

The first command gets the Storage node named ClusterNode01, and then stores it in the $N variable.

The second command gets the node-specific properties of the Storage node in $N, and then stores them in the $Output variable.

The third command gets the specified drive object, and then stores it in the $Pd variable.

### Example 2: Get the node view for a disk
```
PS C:\>$Pd = Get-PhysicalDisk -FriendlyName "PhysicalDisk01"
PS C:\> Get-PhysicalDiskStorageNodeView -PhysicalDisk $Pd
```

The first command gets the disk object for PhysicalDisk01, and then stores it in the $Pd variable.

The second command gets the node-specific properties for the disk in $Pd.

### Example 3: Get the node view for a specified disk and node
```
PS C:\>$N = Get-StorageNode -Name "ClusterNode01"
PS C:\> $Pd = Get-PhysicalDisk -FriendlyName "PhysicalDisk01"
PS C:\> Get-PhysicalDiskStorageNodeView -StorageNode $N -PhysicalDisk $Pd
```

The first command gets the Storage node named ClusterNode01, and then stores it in the $N variable.

The second command gets the physical disk named PhysicalDisk01, and then stores it in the $Pd variable.

The third command gets the node view for the specified Storage node and physical disk.

## PARAMETERS

### -CimSession


```yaml
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalDisk
Specifies a physical disk as a **CimInstance** object.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageNode
Specifies a storage node as a **CimInstance** object.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### MSFT_StorageNodeToPhysicalDisk
Specifies physical disk properties such as health status, operational status, MPIO status, MPIO load balancing policy, MPIO path IDs, MPIO path state, and IDs of the physical disk object and Storage node object.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-DiskStorageNodeView](./Get-DiskStorageNodeView.md)

[Get-StorageEnclosureStorageNodeView](./Get-StorageEnclosureStorageNodeView.md)

