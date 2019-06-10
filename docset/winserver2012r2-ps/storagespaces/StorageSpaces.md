---
Module Name: StorageSpaces
Module Guid: D84E3C43-EEA6-471E-AD89-68BEAE6F1482
Download Help Link: http://go.microsoft.com/fwlink/?linkid=237119
Help Version: 4.0.1.0
Locale: en-US
title: StorageSpaces
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 1abbed1a-ec33-4df5-9135-7e144a34e0bf
ms.author: v-anbarr
ms.reviewer: brianlic
---

# StorageSpaces Module
## Description
{{Manually Enter Description Here}}

## StorageSpaces Cmdlets
### [Disable-StorageSpacesMpioSupport](./Disable-StorageSpacesMpioSupport.md)
Prevents MPIO from claiming serial attached SCSI (SAS) disks on the local computer, and clears the default Load Balance policy configured for disks with MSDSM.

### [Enable-StorageSpacesMpioSupport](./Enable-StorageSpacesMpioSupport.md)
Installs and optimizes the configuration of MPIO for Storage Spaces with serial attached SCSI (SAS) disks on the local computer.

### [Get-AvailableDriveLetter](./Get-AvailableDriveLetter.md)
Returns an array of the available drive letters.

### [Get-SpacesConfiguration](./Get-SpacesConfiguration.md)
Gets an object that contains detailed information about the configuration of a Storage Spaces pool.

### [Get-SpacesPhysicalDisk](./Get-SpacesPhysicalDisk.md)
Gets all PhysicalDisk objects that can be used with Storage Spaces to form a storage pool.

### [Get-SpacesPool](./Get-SpacesPool.md)
Gets all storage pools on the Storage Spaces subsystem.

### [Get-SpacesPoolPhysicalDiskHWCounter](./Get-SpacesPoolPhysicalDiskHWCounter.md)
Collects hardware-based reliability counters for all physical disks in a given Storage Spaces pool.

### [Get-SpacesProvider](./Get-SpacesProvider.md)
Gets the storage provider for Storage Spaces.

### [Get-SpacesSubsystem](./Get-SpacesSubsystem.md)
Gets the storage subsystem for Storage Spaces.

### [Get-SpacesVolume](./Get-SpacesVolume.md)
Gets information about volumes created on storage spaces.

### [Get-StorageSpacesMpioConfiguration](./Get-StorageSpacesMpioConfiguration.md)
Returns current MPIO settings for Storage Spaces.

### [New-SpacesPool](./New-SpacesPool.md)
Creates a storage pool on the Storage Spaces subsystem.

### [New-SpacesVolume](./New-SpacesVolume.md)
Creates a storage space and then creates and formats a volume on the storage space.

### [New-StorageSpacesEventLog](./New-StorageSpacesEventLog.md)
Enables logging of notifications for Storage Spaces.

### [Remove-StorageSpacesEventLog](./Remove-StorageSpacesEventLog.md)
Disables logging of notifications for Storage Spaces and removes existing logs.

### [Repair-SpacesConfiguration](./Repair-SpacesConfiguration.md)
Repairs unhealthy resources associated with a Storage Spaces storage pool.

### [Resize-SpacesVolume](./Resize-SpacesVolume.md)
Resizes storage spaces and file system volumes.

### [Test-SpacesConfiguration](./Test-SpacesConfiguration.md)
Tests for unhealthy resources associated with a Storage Spaces storage pool.

