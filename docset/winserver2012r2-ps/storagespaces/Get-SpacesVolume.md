---
author: Kateyanne
description: 
external help file: StorSpaces2_Cmdlets.xml
manager: jasgro
Module Name: StorageSpaces
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/storagespaces/get-spacesvolume?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SpacesVolume
---

# Get-SpacesVolume

## SYNOPSIS
Gets information about volumes created on storage spaces.

## SYNTAX

```
Get-SpacesVolume [[-SpaceFriendlyName] <String>] [-Cluster]
```

## DESCRIPTION
The Get-SpacesVolume cmdlet gets information about volumes created on storage spaces.

## EXAMPLES

### Example 1 - Get information about Storage Spaces volumes
```
PS C:\>Get-SpacesVolume

OperationalStatus         : OK
HealthStatus              : Healthy
DiskUniqueID              : 5BC0854984DDE111BE73F46D0439C015
DriveLetter               : B
VolumeSize                : 318766030848
SizeRemaining             : 318377242624
VolumeObjectID            : \\?\Volume{4985c062-dd84-11e1-be73-f46d0439c015}\
FileSystem                : NTFS
BackingPhysicalDisks      : {ASMT 2105 USB Device, ASMT 2105 USB Device}
PoolFriendlyName          : USB
SpaceFriendlyName         : Backup
StorageSpaceUniqueID      : 5BC0854984DDE111BE73F46D0439C015
IsManualAttach            : False
DetachedReason            : None
SpaceUsageAlertPercentage : {70}



OperationalStatus         : OK
HealthStatus              : Healthy
DiskUniqueID              : EBB5E72780C7E1119CC4F46D0439C015
DriveLetter               : S
VolumeSize                : 1374254243840
SizeRemaining             : 691400519680
VolumeObjectID            : \\?\Volume{27e7b5f2-c780-11e1-9cc4-f46d0439c015}\
FileSystem                : NTFS
BackingPhysicalDisks      : {Seagate ST750LX003-1AC15 SCSI Disk Device, Seagate ST750LX003-1AC15 SCSI Disk Device,
Seagate ST750LX003-1AC15 SCSI Disk Device, Seagate ST750LX003-1AC15 SCSI Disk Device}
PoolFriendlyName          : Internal
SpaceFriendlyName         : Data
StorageSpaceUniqueID      : EBB5E72780C7E1119CC4F46D0439C015
IsManualAttach            : False
DetachedReason            : None
SpaceUsageAlertPercentage : {70}
```

This example gets information about Storage Spaces volumes.

### Example 2 - Get information about clustered Storage Spaces volumes
```
PS C:\>Get-SpacesVolume -Cluster
```

This example gets a list of all storage spaces across all storage pools on the failover cluster that local machine belongs to.
When run on a clustered storage pool, information about the corresponding failover cluster resources are also displayed, as well as the current node owner.

### Example 3 - Get information about a specific Storage Spaces volume
```
PS C:\>Get-SpacesVolume -SpaceFriendlyName Data
OperationalStatus         : OK
HealthStatus              : Healthy
DiskUniqueID              : EBB5E72780C7E1119CC4F46D0439C015
DriveLetter               : S
VolumeSize                : 1374254243840
SizeRemaining             : 691400519680
VolumeObjectID            : \\?\Volume{27e7b5f2-c780-11e1-9cc4-f46d0439c015}\
FileSystem                : NTFS
BackingPhysicalDisks      : {Seagate ST750LX003-1AC15 SCSI Disk Device, Seagate ST750LX003-1AC15 SCSI Disk Device,
Seagate ST750LX003-1AC15 SCSI Disk Device, Seagate ST750LX003-1AC15 SCSI Disk Device}
PoolFriendlyName          : Internal
SpaceFriendlyName         : Data
StorageSpaceUniqueID      : EBB5E72780C7E1119CC4F46D0439C015
IsManualAttach            : False
DetachedReason            : None
SpaceUsageAlertPercentage : {70}
```

This example gets information about a specific Storage Spaces volume.

## PARAMETERS

### -Cluster
Specifies that the cmdlet is run on a failover cluster.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SpaceFriendlyName
Specifies the friendly name of the storage space.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

## INPUTS

### None

## OUTPUTS

### System.Object
This cmdlet returns an object that represents information about volumes created on the Storage Spaces subsystem.

## NOTES

## RELATED LINKS

