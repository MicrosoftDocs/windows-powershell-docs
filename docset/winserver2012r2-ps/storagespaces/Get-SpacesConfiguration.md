---
external help file: StorSpaces2_Cmdlets.xml
Module Name: StorageSpaces
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/storagespaces/get-spacesconfiguration?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SpacesConfiguration
---

# Get-SpacesConfiguration

## SYNOPSIS
Gets an object that contains detailed information about the configuration of a Storage Spaces pool.

## SYNTAX

```
Get-SpacesConfiguration [-StoragePoolFriendlyName] <String>
```

## DESCRIPTION
The Get-SpacesConfiguration cmdlet gets an object that contains detailed status of the specified storage pool, as well as detailed information about all storage spaces and associated volumes.

Note: If the pool in question is clustered, additional details are included about associated failover clustering resources.

## EXAMPLES

### Example 1 - Get Storage Spaces configuration for a local pool
```
PS C:\>Get-SpacesConfiguration -StoragePoolFriendlyName Internal

StoragePoolFriendlyName        : Internal
HealthStatus                   : Healthy
IsReadOnly                     : False
IsClusteredStoragePool         : False
ThinProvisionAlertThreshold    : 70 %
StoragePoolFreeGigabytes       : 1514
StoragePoolUsedSpacePercent    : 45.79
StoragePoolFreeSpacePercent    : 54.21
OperationalStatus              : OK
NumberofPhysicalDisksInPool    : 4
NumberofStorageSpacesInPool    : 1
NumberofUnhealthyPhysicalDisks : 0
NumberofUnhealthyStorageSpaces : 0

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

## PARAMETERS

### -StoragePoolFriendlyName
Specifies the friendly name of the storage pool.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

