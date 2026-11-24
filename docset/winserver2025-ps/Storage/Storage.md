---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
Download Help Link: https://aka.ms/winsvr-2025-pshelp
Help Version: 5.0.0.2
Locale: en-US
Module Guid: 41486f7d-842f-40f1-ace4-8405f9c2ed9b
Module Name: Storage
ms.date: 12/20/2016
title: Storage
---

# Storage Module
## Description
This reference provides cmdlet descriptions and syntax for all Windows Storage Management-specific cmdlets. It lists the cmdlets in alphabetical order based on the verb at the beginning of the cmdlet.

## Storage Cmdlets
### [Add-InitiatorIdToMaskingSet](./Add-InitiatorIdToMaskingSet.md)
Adds an initiator ID to an existing masking set, granting the host associated with the initiator ID access to the virtual disk and target port resources defined in the masking set.

### [Add-PartitionAccessPath](./Add-PartitionAccessPath.md)
Adds an access path such as a drive letter or folder to a partition.

### [Add-PhysicalDisk](./Add-PhysicalDisk.md)
Adds a physical disk to the specified storage pool or manually assigns a physical disk to a specific virtual disk.

### [Add-TargetPortToMaskingSet](./Add-TargetPortToMaskingSet.md)
Adds one or more target ports to a specified masking set, allowing a connection between the target ports, and any virtual disks and initiator IDs that the masking set contains.

### [Add-VirtualDiskToMaskingSet](./Add-VirtualDiskToMaskingSet.md)
Adds a virtual disk to a specified masking set and grants access to the virtual disk to all initiator IDs defined in the masking set.

### [Block-FileShareAccess](./Block-FileShareAccess.md)
Blocks access to a file share.

### [Clear-Disk](./Clear-Disk.md)
Cleans a disk by removing all partition information and un-initializing it, erasing all data on the disk.

### [Clear-FileStorageTier](./Clear-FileStorageTier.md)
Unpins a file from the specified storage tier.

### [Connect-VirtualDisk](./Connect-VirtualDisk.md)
Connects a disconnected virtual disk to the specified computer when using the Windows Storage subsystem.

### [Debug-FileShare](./Debug-FileShare.md)
Finds problems with a file share and recommends solutions.

### [Debug-StorageSubSystem](./Debug-StorageSubSystem.md)
Finds problems with a storage subsystem and recommends solutions.

### [Debug-Volume](./Debug-Volume.md)
Finds problems with a volume and recommends solutions.

### [Disable-PhysicalDiskIdentification](./Disable-PhysicalDiskIdentification.md)
Turns off the identification LED on the specified physical disk.

### [Disable-StorageEnclosureIdentification](./Disable-StorageEnclosureIdentification.md)
Turns off the identification LED on a storage enclosure or the slots for individual disks.

### [Disable-StorageHighAvailability](./Disable-StorageHighAvailability.md)
Disables a Storage resource.

### [Disable-StorageMaintenanceMode](./Disable-StorageMaintenanceMode.md)
Disables storage maintenance mode on a fault domain.

### [Disconnect-VirtualDisk](./Disconnect-VirtualDisk.md)
Disconnects a virtual disk from the specified computer, revoking access to the virtual disk.

### [Dismount-DiskImage](./Dismount-DiskImage.md)
Dismounts a disk image (virtual hard disk or ISO) so that it can no longer be accessed as a disk.

### [Enable-PhysicalDiskIdentification](./Enable-PhysicalDiskIdentification.md)
Enables the identification LED on the specified physical disk.

### [Enable-StorageEnclosureIdentification](./Enable-StorageEnclosureIdentification.md)
Enables the identification LED on a storage enclosure or the slots for individual disks.

### [Enable-StorageHighAvailability](./Enable-StorageHighAvailability.md)
Enables a disk to be added to the failover cluster.

### [Enable-StorageMaintenanceMode](./Enable-StorageMaintenanceMode.md)
Enables storage maintenance mode on a device.

### [Format-Volume](./Format-Volume.md)
Formats one or more existing volumes or a new volume on an existing partition.

### [Get-DedupProperties](./Get-DedupProperties.md)
Gets Data Deduplication information.

### [Get-Disk](./Get-Disk.md)
Gets one or more disks visible to the operating system.

### [Get-DiskImage](./Get-DiskImage.md)
Gets one or more disk image objects (virtual hard disk or ISO).

### [Get-DiskStorageNodeView](./Get-DiskStorageNodeView.md)
Gets the view of a disk from a storage node.

### [Get-FileIntegrity](./Get-FileIntegrity.md)
Gets integrity information for a file on an ReFS volume.

### [Get-FileShare](./Get-FileShare.md)
Retrieves file share objects and their properties.

### [Get-FileShareAccessControlEntry](./Get-FileShareAccessControlEntry.md)
Retrieves an access control entry for the share corresponding to a single account.

### [Get-FileStorageTier](./Get-FileStorageTier.md)
Gets the files assigned to a Storage tier on a volume, and their status.

### [Get-InitiatorId](./Get-InitiatorId.md)
Gets the InitiatorID objects for the specified iSCSI initiators.

### [Get-InitiatorPort](./Get-InitiatorPort.md)
Gets one or more host bus adapter (HBA) initiator ports.

### [Get-MaskingSet](./Get-MaskingSet.md)
Gets masking sets.

### [Get-OffloadDataTransferSetting](./Get-OffloadDataTransferSetting.md)
Returns offloaded data transfer (ODX) settings for the specified subsystem.

### [Get-Partition](./Get-Partition.md)
Returns a list of all partition objects visible on all disks, or optionally a filtered list using specified parameters.

### [Get-PartitionSupportedSize](./Get-PartitionSupportedSize.md)
Returns information on supported partition sizes for the specified Disk object.

### [Get-PhysicalDisk](./Get-PhysicalDisk.md)
Gets a list of all PhysicalDisk objects visible across any available Storage Management Providers, or optionally a filtered list.

### [Get-PhysicalDiskStorageNodeView](./Get-PhysicalDiskStorageNodeView.md)
Gets the node view of a physical disk.

### [Get-PhysicalExtent](./Get-PhysicalExtent.md)
Gets physical allocations for a physical disk, storage tier, or virtual disk.

### [Get-PhysicalExtentAssociation](./Get-PhysicalExtentAssociation.md)
Gets the physical disk, storage tier, or virtual disk that is associated with a physical extent.

### [Get-ResiliencySetting](./Get-ResiliencySetting.md)
Gets the resiliency settings (also known as storage layouts) available for creating virtual disks on the specified storage subsystem.

### [Get-StorageAdvancedProperty](./Get-StorageAdvancedProperty.md)
Gets the advanced properties on a storage device.

### [Get-StorageDiagnosticInfo](./Get-StorageDiagnosticInfo.md)
Gets Storage diagnostic information.

### [Get-StorageEnclosure](./Get-StorageEnclosure.md)
Gets storage enclosures.

### [Get-StorageEnclosureStorageNodeView](./Get-StorageEnclosureStorageNodeView.md)
Gets the node view of a Storage enclosure.

### [Get-StorageEnclosureVendorData](./Get-StorageEnclosureVendorData.md)
Gets vendor-specific data for an enclosure.

### [Get-StorageFaultDomain](./Get-StorageFaultDomain.md)
Gets a Storage fault domain object.

### [Get-StorageFileServer](./Get-StorageFileServer.md)
Gets a storage file server.

### [Get-StorageFirmwareInformation](./Get-StorageFirmwareInformation.md)
Gets information about firmware on a storage object.

### [Get-StorageHealthAction](./Get-StorageHealthAction.md)
Gets health-related system activities.

### [Get-StorageHealthReport](./Get-StorageHealthReport.md)
Gets a storage health report.

### [Get-StorageHealthSetting](./Get-StorageHealthSetting.md)
Gets storage health service settings.

### [Get-StorageJob](./Get-StorageJob.md)
Returns information about long-running Storage module jobs, such as a repair task.

### [Get-StorageNode](./Get-StorageNode.md)
Gets storage nodes.

### [Get-StoragePool](./Get-StoragePool.md)
Gets a specific storage pool, or a set of StoragePool objects either from all storage subsystems across all storage providers, or optionally a filtered subset based on specific parameters.

### [Get-StorageProvider](./Get-StorageProvider.md)
Returns a list of the storage providers available on the local computer.

### [Get-StorageReliabilityCounter](./Get-StorageReliabilityCounter.md)
Gets storage reliability counters.

### [Get-StorageSetting](./Get-StorageSetting.md)
Gets a StorageSetting object.

### [Get-StorageSubsystem](./Get-StorageSubsystem.md)
Gets one or more StorageSubsystem objects.

### [Get-StorageTier](./Get-StorageTier.md)
Gets storage tiers on Windows Storage subsystems.

### [Get-StorageTierSupportedSize](./Get-StorageTierSupportedSize.md)
Gets the minimum and maximum possible sizes of a storage tier.

### [Get-SupportedClusterSizes](./Get-SupportedClusterSizes.md)
Gets the supported cluster sizes.

### [Get-SupportedFileSystems](./Get-SupportedFileSystems.md)
Gets the file system choices for a specified volume.

### [Get-TargetPort](./Get-TargetPort.md)
Returns a TargetPort object associated with a specific port address and connection type.

### [Get-TargetPortal](./Get-TargetPortal.md)
Returns a TargetPortal object.

### [Get-VirtualDisk](./Get-VirtualDisk.md)
Returns a list of VirtualDisk objects, across all storage pools, across all providers, or optionally a filtered subset based on provided criteria.

### [Get-VirtualDiskSupportedSize](./Get-VirtualDiskSupportedSize.md)
Returns all sizes supported by a storage pool for virtual disk creation based on the specified resiliency setting name.

### [Get-Volume](./Get-Volume.md)
Gets the specified Volume object, or all Volume objects if no filter is provided.

### [Get-VolumeCorruptionCount](./Get-VolumeCorruptionCount.md)
Gets a count of the file system errors on the NTFS volume.

### [Get-VolumeScrubPolicy](./Get-VolumeScrubPolicy.md)
Gets the status of the volume scrub policy.

### [Grant-FileShareAccess](./Grant-FileShareAccess.md)
Grants access to a file share.

### [Hide-VirtualDisk](./Hide-VirtualDisk.md)
Hides the virtual disk from the host when the Storage Management Provider in use does not support masking sets.

### [Initialize-Disk](./Initialize-Disk.md)
Initializes a RAW disk for first time use, enabling the disk to be formatted and used to store data.

### [Mount-DiskImage](./Mount-DiskImage.md)
Mounts a previously created disk image (virtual hard disk or ISO), making it appear as a normal disk.

### [New-FileShare](./New-FileShare.md)
Creates an access point for a remote file share.

### [New-MaskingSet](./New-MaskingSet.md)
Creates a new masking set.

### [New-Partition](./New-Partition.md)
Creates a new partition on an existing Disk object.

### [New-StorageFileServer](./New-StorageFileServer.md)
Creates a storage file server.

### [New-StoragePool](./New-StoragePool.md)
Creates a new storage pool using a group of physical disks.

### [New-StorageSubsystemVirtualDisk](./New-StorageSubsystemVirtualDisk.md)
Allows the creation of a VirtualDisk object on a storage subsystem that does not support creation of storage pools.

### [New-StorageTier](./New-StorageTier.md)
Creates a storage tier.

### [New-VirtualDisk](./New-VirtualDisk.md)
Creates a new virtual disk in the specified storage pool.

### [New-VirtualDiskClone](./New-VirtualDiskClone.md)
Creates a new clone of a specified virtual disk.

### [New-VirtualDiskSnapshot](./New-VirtualDiskSnapshot.md)
Creates a new snapshot of the specified virtual disk.

### [New-Volume](./New-Volume.md)
Creates a volume with the specified file system.

### [Optimize-StoragePool](./Optimize-StoragePool.md)
Optimizes a Storage pool.

### [Optimize-Volume](./Optimize-Volume.md)
Optimizes a volume.

### [Register-StorageSubsystem](./Register-StorageSubsystem.md)
Connects to storage subsystems on a remote computer.

### [Remove-FileShare](./Remove-FileShare.md)
Removes a file share.

### [Remove-InitiatorId](./Remove-InitiatorId.md)
Removes an initiator identifier (ID).

### [Remove-InitiatorIdFromMaskingSet](./Remove-InitiatorIdFromMaskingSet.md)
Removes an initiator identifier (ID) from a masking set.

### [Remove-MaskingSet](./Remove-MaskingSet.md)
Removes a masking set.

### [Remove-Partition](./Remove-Partition.md)
Deletes the specified Partition object on an existing disk and any underlying Volume objects.

### [Remove-PartitionAccessPath](./Remove-PartitionAccessPath.md)
Removes an access path such as a drive letter or folder from a partition.

### [Remove-PhysicalDisk](./Remove-PhysicalDisk.md)
Removes a physical disk from a specified storage pool.

### [Remove-StorageFileServer](./Remove-StorageFileServer.md)
Removes a file server.

### [Remove-StorageHealthSetting](./Remove-StorageHealthSetting.md)
Removes a storage health service setting.

### [Remove-StoragePool](./Remove-StoragePool.md)
Deletes a storage pool and associated VirtualDisk objects.

### [Remove-StorageTier](./Remove-StorageTier.md)
Removes storage tiers from a storage pool.

### [Remove-TargetPortFromMaskingSet](./Remove-TargetPortFromMaskingSet.md)
Removes a specified target port from a masking set.

### [Remove-VirtualDisk](./Remove-VirtualDisk.md)
Deletes an existing virtual disk and reclaims the used space for use by other virtual disks in the same storage pool.

### [Remove-VirtualDiskFromMaskingSet](./Remove-VirtualDiskFromMaskingSet.md)
Removes a virtual disk from a specified masking set to block access to the virtual disk by an InitiatorIds object defined in the masking set.

### [Rename-MaskingSet](./Rename-MaskingSet.md)
Renames an existing masking set.

### [Repair-FileIntegrity](./Repair-FileIntegrity.md)
Repairs a corrupted file on an NTFS or ReFS volume.

### [Repair-VirtualDisk](./Repair-VirtualDisk.md)
Performs repairs on a virtual disk that is unhealthy.

### [Repair-Volume](./Repair-Volume.md)
Performs repairs on a volume.

### [Reset-PhysicalDisk](./Reset-PhysicalDisk.md)
Resets the status of a physical disk.

### [Reset-StorageReliabilityCounter](./Reset-StorageReliabilityCounter.md)
Resets storage reliability counters for a disk.

### [Resize-Partition](./Resize-Partition.md)
Resizes a partition and the underlying file system.

### [Resize-StorageTier](./Resize-StorageTier.md)
Increases the size of storage tiers.

### [Resize-VirtualDisk](./Resize-VirtualDisk.md)
Resizes an existing virtual disk to be larger or smaller.

### [Revoke-FileShareAccess](./Revoke-FileShareAccess.md)
Revokes access to a file share.

### [Set-Disk](./Set-Disk.md)
Takes a Disk object or unique disk identifiers and a set of attributes, and updates the physical disk on the system.

### [Set-FileIntegrity](./Set-FileIntegrity.md)
Sets integrity for a file on an ReFS volume.

### [Set-FileShare](./Set-FileShare.md)
Modifies a file share.

### [Set-FileStorageTier](./Set-FileStorageTier.md)
Assigns a file to a storage tier.

### [Set-InitiatorPort](./Set-InitiatorPort.md)
Sets properties on the InitiatorPort object.

### [Set-Partition](./Set-Partition.md)
Sets attributes of a partition, such as active, read-only, and offline states.

### [Set-PhysicalDisk](./Set-PhysicalDisk.md)
Sets attributes on a specific physical disk.

### [Set-ResiliencySetting](./Set-ResiliencySetting.md)
Modifies the properties of the specified resiliency setting name.

### [Set-StorageFileServer](./Set-StorageFileServer.md)
Modifies a storage file server.

### [Set-StorageHealthSetting](./Set-StorageHealthSetting.md)
Modifies a storage health service setting.

### [Set-StoragePool](./Set-StoragePool.md)
Modifies the properties of the specified storage pool.

### [Set-StorageProvider](./Set-StorageProvider.md)
Modifies whether to enable the SMP provider cache.

### [Set-StorageSetting](./Set-StorageSetting.md)
Adjusts or configures current storage settings of the StorageSetting object.

### [Set-StorageSubsystem](./Set-StorageSubsystem.md)
Modifies the properties of a StorageSubsystem object.

### [Set-StorageTier](./Set-StorageTier.md)
Modifies a storage tier.

### [Set-VirtualDisk](./Set-VirtualDisk.md)
Modifies the attributes of an existing virtual disk.

### [Set-Volume](./Set-Volume.md)
Sets or changes the file system label of an existing volume.

### [Set-VolumeScrubPolicy](./Set-VolumeScrubPolicy.md)
Sets the status of the volume scrub policy.

### [Show-VirtualDisk](./Show-VirtualDisk.md)
Makes a virtual disk available to a host.

### [Start-StorageDiagnosticLog](./Start-StorageDiagnosticLog.md)
Starts Storage diagnostic logging.

### [Stop-StorageDiagnosticLog](./Stop-StorageDiagnosticLog.md)
Stops a Storage diagnostic log.

### [Stop-StorageJob](./Stop-StorageJob.md)
Stops storage job.

### [Unblock-FileShareAccess](./Unblock-FileShareAccess.md)
Unblocks access to a file share.

### [Unregister-StorageSubsystem](./Unregister-StorageSubsystem.md)
Disconnects from storage subsystems on a remote computer.

### [Update-Disk](./Update-Disk.md)
Updates cached information about the specified Disk object only

### [Update-HostStorageCache](./Update-HostStorageCache.md)
Initiates an update on the host storage cache to reflect the current status of storage.

### [Update-StorageFirmware](./Update-StorageFirmware.md)
Updates the firmware on a storage device.

### [Update-StoragePool](./Update-StoragePool.md)
Updates the metadata of a Windows Server 2012 R2 storage pool.

### [Update-StorageProviderCache](./Update-StorageProviderCache.md)
Updates the cache of the service for a particular provider and associated child objects.

### [Write-VolumeCache](./Write-VolumeCache.md)
Writes the file system cache to disk.



