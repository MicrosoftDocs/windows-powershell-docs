---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/new-volume?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-Volume
---

# New-Volume

## SYNOPSIS
Creates a volume with the specified file system.

## SYNTAX

### ByStoragePool
```
New-Volume [-StoragePool] <CimInstance> -FriendlyName <String> [-FileSystem <FileSystemType>]
 [-AccessPath <String>] [-DriveLetter <Char>] [-AllocationUnitSize <UInt32>] [-Size <UInt64>]
 [-ResiliencySettingName <String>] [-ProvisioningType <ProvisioningType>] [-MediaType <MediaType>]
 [-PhysicalDiskRedundancy <UInt16>] [-NumberOfColumns <UInt16>] [-NumberOfGroups <UInt16>]
 [-StorageTiers <CimInstance[]>] [-StorageTierFriendlyNames <String[]>] [-StorageTierSizes <UInt64[]>]
 [-WriteCacheSize <UInt64>] [-ReadCacheSize <UInt64>] [-UseMaximumSize] [-CimSession <CimSession>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStoragePoolFriendlyName
```
New-Volume -StoragePoolFriendlyName <String> -FriendlyName <String> [-FileSystem <FileSystemType>]
 [-AccessPath <String>] [-DriveLetter <Char>] [-AllocationUnitSize <UInt32>] [-Size <UInt64>]
 [-ResiliencySettingName <String>] [-ProvisioningType <ProvisioningType>] [-MediaType <MediaType>]
 [-PhysicalDiskRedundancy <UInt16>] [-NumberOfColumns <UInt16>] [-NumberOfGroups <UInt16>]
 [-StorageTiers <CimInstance[]>] [-StorageTierFriendlyNames <String[]>] [-StorageTierSizes <UInt64[]>]
 [-WriteCacheSize <UInt64>] [-ReadCacheSize <UInt64>] [-UseMaximumSize] [-CimSession <CimSession>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStoragePoolName
```
New-Volume -StoragePoolName <String> -FriendlyName <String> [-FileSystem <FileSystemType>]
 [-AccessPath <String>] [-DriveLetter <Char>] [-AllocationUnitSize <UInt32>] [-Size <UInt64>]
 [-ResiliencySettingName <String>] [-ProvisioningType <ProvisioningType>] [-MediaType <MediaType>]
 [-PhysicalDiskRedundancy <UInt16>] [-NumberOfColumns <UInt16>] [-NumberOfGroups <UInt16>]
 [-StorageTiers <CimInstance[]>] [-StorageTierFriendlyNames <String[]>] [-StorageTierSizes <UInt64[]>]
 [-WriteCacheSize <UInt64>] [-ReadCacheSize <UInt64>] [-UseMaximumSize] [-CimSession <CimSession>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStoragePoolUniqueId
```
New-Volume -StoragePoolUniqueId <String> -FriendlyName <String> [-FileSystem <FileSystemType>]
 [-AccessPath <String>] [-DriveLetter <Char>] [-AllocationUnitSize <UInt32>] [-Size <UInt64>]
 [-ResiliencySettingName <String>] [-ProvisioningType <ProvisioningType>] [-MediaType <MediaType>]
 [-PhysicalDiskRedundancy <UInt16>] [-NumberOfColumns <UInt16>] [-NumberOfGroups <UInt16>]
 [-StorageTiers <CimInstance[]>] [-StorageTierFriendlyNames <String[]>] [-StorageTierSizes <UInt64[]>]
 [-WriteCacheSize <UInt64>] [-ReadCacheSize <UInt64>] [-UseMaximumSize] [-CimSession <CimSession>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByDisk
```
New-Volume [-Disk] <CimInstance> -FriendlyName <String> [-FileSystem <FileSystemType>] [-AccessPath <String>]
 [-DriveLetter <Char>] [-AllocationUnitSize <UInt32>] [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByDiskNumber
```
New-Volume [-DiskNumber] <UInt32> -FriendlyName <String> [-FileSystem <FileSystemType>] [-AccessPath <String>]
 [-DriveLetter <Char>] [-AllocationUnitSize <UInt32>] [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByDiskPath
```
New-Volume -DiskPath <String> -FriendlyName <String> [-FileSystem <FileSystemType>] [-AccessPath <String>]
 [-DriveLetter <Char>] [-AllocationUnitSize <UInt32>] [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByDiskUniqueId
```
New-Volume -DiskUniqueId <String> -FriendlyName <String> [-FileSystem <FileSystemType>] [-AccessPath <String>]
 [-DriveLetter <Char>] [-AllocationUnitSize <UInt32>] [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **New-Volume** cmdlet creates a volume with the specified file system.
The cmdlet manages the creation of the virtual disk with the specified size and resiliency setting, initializes the disk, creates a partition on it and formats the volume with the specified file system, including Cluster Shared Volumes (CSVs).

## EXAMPLES

### Example 1: Create a volume on a mirror space
```powershell
PS C:\> New-Volume -StoragePoolName "CompanyData" -FriendlyName "TestVolume" -Size 10GB -ResiliencySettingName "Mirror" -FileSystem NTFS -AccessPath "M: "-ProvisioningType Fixed
```

This command creates a new storage space in the CompanyData pool using the Mirror resiliency setting and fixed provisioning, and then formats the volume with the NTFS file system and assigns drive letter M.

### Example 2: Create a volume on a new tiered storage space
```powershell
PS C:\>New-Volume -StoragePoolFriendlyName "CompanyData" -FriendlyName "UserData" -AccessPath "M:" -ResiliencySettingName "Mirror" -ProvisioningType "Fixed" -StorageTiers (Get-StorageTier -FriendlyName "*SSD*"), (Get-StorageTier -FriendlyName "*HDD*") -StorageTierSizes 20GB, 80GB -FileSystem NTFS
```
This command creates new storage space in the CompanyData pool using the Mirror resiliency setting, fixed provisioning, a 20 GB SSD storage tier, and an 80 GB HDD storage tier, and then formats the volume with the NTFS file system and assigns drive letter M.


### Example 3: Create a volume on disk
```powershell
PS C:\>Get-Disk | Where-Object OperationalStatus -eq 'Offline'|
         Initialize-Disk -PartitionStyle GPT -PassThru |
            New-Volume -FileSystem NTFS -DriveLetter F -FriendlyName 'New-Volume'
````
This command initializes a new disk added to a host then creates a new volume on each new disk.

## PARAMETERS

### -AccessPath
Specifies a drive letter, or a mount point.

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

### -AllocationUnitSize
Specifies the allocation unit size to use when creating the volume.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Disk
Specifies a **Disk** object.
To obtain a **Disk** object, use the Get-Disk cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByDisk
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DiskNumber
Specifies the disk number of the disk on which to create a volume.

```yaml
Type: UInt32
Parameter Sets: ByDiskNumber
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskPath
Specifies the path of the disk on which to create a volume.

```yaml
Type: String
Parameter Sets: ByDiskPath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskUniqueId
Specifies the ID of the disk on which to create a volume.

```yaml
Type: String
Parameter Sets: ByDiskUniqueId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DriveLetter
Specifies the drive letter of the disk on which to create a volume.

```yaml
Type: Char
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileSystem
Specified the file system to use on the volume.
The acceptable values for this parameter are: NTFS, and ReFS, as well as the cluster shared volume versions of these file systems for use on a scale-out file server: CSVFS_NTFS, and CSVFS_ReFS,

```yaml
Type: FileSystemType
Parameter Sets: (All)
Aliases:
Accepted values: NTFS, ReFS, CSVFS_NTFS, CSVFS_ReFS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Specifies the friendly name to use for the volume.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MediaType
Specifies the media type of the storage tier.
The cmdlet creates the storage tier for the media type that you specify.
The acceptable values for this parameter are:

- SSD
- SCM
- HDD

Use SCM for storage-class memory such as NVDIMMs.

```yaml
Type: MediaType
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
Aliases:
Accepted values: HDD, SSD, SCM

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumberOfColumns
Specifies the number of columns to use when creating the volume on a Windows Storage subsystem.
Columns represent the number of underlying physical disks across which one stripe of data for a volume is written.

```yaml
Type: UInt16
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumberOfGroups
Specifies the number of groups used by Local Reconstruction Coding (LRC) with a dual parity virtual disk.
We recommend omitting this parameter and using the defaults.

```yaml
Type: UInt16
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalDiskRedundancy
Specifies the physical disk redundancy value to use during the creation of a volume on a Windows Storage subsystem.
This value represents how many failed physical disks the volume can tolerate without data loss.
Redundancy values are as follows:

- For two-way mirror spaces, the virtual disk can tolerate 1 failed physical disk without data loss.
- For three-way mirror spaces, the virtual disk can tolerate 2 failed physical disks without data loss.
- For single-parity spaces, the virtual disk can tolerate 1 failed physical disk without data loss.
- For dual-parity spaces the virtual disk can tolerate 2 failed physical disks without data loss.

```yaml
Type: UInt16
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProvisioningType
Specifies the type of provisioning.
The acceptable values for this parameter are: Fixed and Thin.
Specify Fixed for storage spaces that use storage tiers or a clustered storage pool

```yaml
Type: ProvisioningType
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
Aliases:
Accepted values: Unknown, Thin, Fixed

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReadCacheSize
This parameter is no longer supported.

```yaml
Type: UInt64
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResiliencySettingName
Specifies the resiliency setting (storage layout) to use for the volume.
Acceptable values vary by storage subsystem.

Allowed values for the Windows Storage subsystem are: Simple, Mirror, or Parity.
By default, when you specify Mirror, Storage Spaces creates a two-way mirror, and when you specify Parity, Storage Spaces creates a single-parity space.

To create a three-way mirror space, specify 3 for the *NumberofDataCopies* parameter or 2 for the *PhysicalDiskRedundancy* parameter.

To create a dual-parity space, specify 2 for the *PhysicalDiskRedundancy* parameter and Fixed provisioning for the *ProvisioningType* parameter.

```yaml
Type: String
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Size
Specifies the size of the volume to create.
The default unit is bytes.
To specify a different unit, enter the size followed by one of the following unit values, with no spaces: Bytes, KB, MB, GB, or TB.

```yaml
Type: UInt64
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePool
Specifies the storage pool object in which you want to create a volume.
To obtain a storage pool object, use the Get-StoragePool cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStoragePool
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StoragePoolFriendlyName
Specifies the friendly name of the storage pool in which to create a volume.

```yaml
Type: String
Parameter Sets: ByStoragePoolFriendlyName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePoolName
Specifies the name of the storage pool in which to create a volume.

```yaml
Type: String
Parameter Sets: ByStoragePoolName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePoolUniqueId
Specifies the unique ID of the storage pool in which to create a volume.

```yaml
Type: String
Parameter Sets: ByStoragePoolUniqueId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageTierFriendlyNames
Specifies the names of storage tiers to use when creating the volume.

```yaml
Type: String[]
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageTierSizes
Specifies how big to make each storage tier on this volume.

```yaml
Type: UInt64[]
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageTiers
Specifies the storage tier objects to use when creating the volume.

```yaml
Type: CimInstance[]
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseMaximumSize
Indicates that this cmdlet creates the largest volumn possible.

```yaml
Type: SwitchParameter
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WriteCacheSize
Specifies the size of the write-back cache.
The cmdlet creates the write-back cache of the size that you specify when the cmdlet creates the virtual disk space.

The following describes the behavior of this parameter based on the value that you specify:

1. If you do not specify this parameter, the cmdlet sets the value of the **WriteCacheSizeDefault** property from the storage pool.
1. The default setting of **WriteCacheSizeDefault** for a storage pool is Auto, which specifies that Windows Server automatically selects the optimal write-back cache size for your configuration.
You can change the value of **WriteCacheSizeDefault** to a concrete value at any time.
1. The Auto setting for *WriteCacheSize* operates as follows:
    1. If any of the following is true, Auto is set to 1 GB:
        1. The storage pool contains at least N drives with enough capacity and you set the Usage parameter to Journal.
        N = 1 for simple spaces, N = 2 for two-way mirror and single parity, N = 3 for three-way mirror and dual parity.
        1. The storage pool contains at least N drives with enough capacity and the media type of the virtual disk is set to SSD.
        N = 1 for simple spaces, N = 2 for two-way mirror and single parity, N = 3 for three-way mirror and dual parity.
    1. Otherwise, Auto is set to 0 (no log) for simple and mirror spaces, and 32 MB for parity spaces.
1. If you specify Auto or 0 (zero) for this parameter and the storage space is not a parity space, the cmdlet verifies that either 3.a.i or 3.a.ii is true.
If either 3.a.i or 3.a.ii is not true, you cannot set *WriteCacheSize* to Auto or 0.
    1. The objective of these conditions is to help you avoid scenarios in which you force the creation of a write-back cache in situations that result in slower performance.

```yaml
Type: UInt64
Parameter Sets: ByStoragePool, ByStoragePoolFriendlyName, ByStoragePoolName, ByStoragePoolUniqueId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
You can use the pipeline operator to pass an MSFT_StoragePool object to the *InputObject* parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/Storage/MSFT_Volume
This cmdlet outputs an object that represents the newly created volume.

## NOTES
* To create a volume on a new storage space with enclosure-awareness enabled (providing resiliency for an entire JBOD enclosure failure), use the **Set-StoragePool** cmdlet with the *-EnclosureAwareDefault $true* parameter to set the storage pool to create storage spaces with enclosure awareness enabled by default.
* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Debug-Volume](./Debug-Volume.md)

[Format-Volume](./Format-Volume.md)

[Get-Disk](./Get-Disk.md)

[Get-StoragePool](./Get-StoragePool.md)

[Get-Volume](./Get-Volume.md)

[Optimize-Volume](./Optimize-Volume.md)

[Repair-Volume](./Repair-Volume.md)

[Set-Volume](./Set-Volume.md)

