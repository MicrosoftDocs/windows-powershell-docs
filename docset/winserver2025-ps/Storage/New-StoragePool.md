---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageSubSystem.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/new-storagepool?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-StoragePool
---

# New-StoragePool

## SYNOPSIS
Creates a new storage pool using a group of physical disks.

## SYNTAX

### ByFriendlyName (Default)
```
New-StoragePool [-StorageSubSystemFriendlyName] <String[]> -FriendlyName <String> [-Usage <Usage>]
 [-OtherUsageDescription <String>] -PhysicalDisks <CimInstance[]> [-ProvisioningTypeDefault <ProvisioningType>]
 [-MediaTypeDefault <MediaType>] [-EnclosureAwareDefault <Boolean>]
 [-FaultDomainAwarenessDefault <FaultDomainType>] [-ResiliencySettingNameDefault <String>]
 [-LogicalSectorSizeDefault <UInt64>] [-WriteCacheSizeDefault <UInt64>] [-AutoWriteCacheSize <Boolean>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
New-StoragePool -StorageSubSystemUniqueId <String[]> -FriendlyName <String> [-Usage <Usage>]
 [-OtherUsageDescription <String>] -PhysicalDisks <CimInstance[]> [-ProvisioningTypeDefault <ProvisioningType>]
 [-MediaTypeDefault <MediaType>] [-EnclosureAwareDefault <Boolean>]
 [-FaultDomainAwarenessDefault <FaultDomainType>] [-ResiliencySettingNameDefault <String>]
 [-LogicalSectorSizeDefault <UInt64>] [-WriteCacheSizeDefault <UInt64>] [-AutoWriteCacheSize <Boolean>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByName
```
New-StoragePool -StorageSubSystemName <String[]> -FriendlyName <String> [-Usage <Usage>]
 [-OtherUsageDescription <String>] -PhysicalDisks <CimInstance[]> [-ProvisioningTypeDefault <ProvisioningType>]
 [-MediaTypeDefault <MediaType>] [-EnclosureAwareDefault <Boolean>]
 [-FaultDomainAwarenessDefault <FaultDomainType>] [-ResiliencySettingNameDefault <String>]
 [-LogicalSectorSizeDefault <UInt64>] [-WriteCacheSizeDefault <UInt64>] [-AutoWriteCacheSize <Boolean>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### InputObject (cdxml)
```
New-StoragePool -InputObject <CimInstance[]> -FriendlyName <String> [-Usage <Usage>]
 [-OtherUsageDescription <String>] -PhysicalDisks <CimInstance[]> [-ProvisioningTypeDefault <ProvisioningType>]
 [-MediaTypeDefault <MediaType>] [-EnclosureAwareDefault <Boolean>]
 [-FaultDomainAwarenessDefault <FaultDomainType>] [-ResiliencySettingNameDefault <String>]
 [-LogicalSectorSizeDefault <UInt64>] [-WriteCacheSizeDefault <UInt64>] [-AutoWriteCacheSize <Boolean>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **New-StoragePool** cmdlet creates a new storage pool using a group of physical disks exposed by a specific storage subsystem.

## EXAMPLES

### Example 1: Create a new storage pool using Storage Spaces
```
PS C:\> $PhysicalDisks = (Get-PhysicalDisk -CanPool $True)
PS C:\> New-StoragePool -FriendlyName CompanyData -StorageSubsystemFriendlyName "Windows Storage*" -PhysicalDisks $PhysicalDisks
```

The first line uses the **Get-PhysicalDisk** cmdlet to get all PhysicalDisk objects that are not yet in a (concrete) storage pool and assigns the array of objects to the `$PhysicalDisks` variable.

The second line creates a new storage pool using the `$PhysicalDisks` variable to specify the disks to include from the WindowsStorage subsystem (specified with a wildcard * to remove the need to modify the friendly name for different computers).

This example creates a new storage pool named CompanyData using the Storage Spaces subsytem, using the minimum parameters, and assuming that there are no other storage subsystems attached to the computer that have available disks.

### Example 2: Create a new pool and set defaults for virtual disks
```
PS C:\> $PhysicalDisks = (Get-PhysicalDisk -CanPool $True)
PS C:\> New-StoragePool -FriendlyName CompanyData -StorageSubsystemFriendlyName "Windows Storage*" -PhysicalDisks $PhysicalDisks -ResiliencySettingNameDefault Mirror -ProvisioningTypeDefault Thin -Verbose
```

This example creates a new storage pool named CompanyData using the Windows Storage subsystem and sets default values for virtual disk creation.

### Example 3: Create a new storage pool, virtual disk, partition, and volume

The first line (`$PhysicalDisks = …`) gets the storage subsystem object for the Windows Storage subsystem, passes it to the **Get-PhysicalDisk** cmdlet, which then gets the physical disks in the specified subsystem that are available to add to a storage pool, and assigns these disks to the $PhysicalDisks variable.

The second line of the command has five parts, connected by the pipeline (|).

The first part (`New-StoragePool …`) creates a new storage pool using the physical disks in the `$PhysicalDisks` variable and then passes the new storage pool down the pipeline. All of the following commands are logically part of one command and should be entered as such.

The second part (`New-VirtualDisk …`) creates a new virtual disk on the passed in storage pool and then passes the new virtual disk down the pipeline.
The third part (`Initialize-Disk …`) initializes the disk that was passed in and then passes the disk down the pipeline.

The fourth part (`New-Partition …`) creates a new partition on the disk that was passed in, assigns it the next available drive letter, and then passes the partition down the pipeline.

The final part of the command (`Format-Volume`) formats the partition that was passed in.
```
PS C:\> $PhysicalDisks = Get-StorageSubSystem -FriendlyName "Windows Storage*" | Get-PhysicalDisk -CanPool $True
PS C:\> New-StoragePool -FriendlyName "CompanyData" -StorageSubsystemFriendlyName "Windows Storage*" -PhysicalDisks $PhysicalDisks | New-VirtualDisk -FriendlyName "UserData" -Size 100GB -ProvisioningType Thin | Initialize-Disk -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume
```

This example creates a new storage pool, and then makes use of the pipeline to create a new virtual disk in the pool, initialize the disk, create a new partition on the disk, and then format the new partition (volume).
Alternatively you can use the New-Volume cmdlet to achieve a similar result in a single command.

## PARAMETERS

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

### -AutoWriteCacheSize
Indicates whether to set the size of the write-back cache to 1 GB for all types of storage spaces, which include simple, mirror, and parity, to create from the pool.
If the number or size of the solid-state drives (SSDs) or journal disks in the storage pool is not sufficient and you specify a value of $True for this parameter, the cmdlet sets the write-back cache size to 0 for simple and mirror spaces, and to 32 MB for parity spaces.

```yaml
Type: Boolean
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
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnclosureAwareDefault
Specifies the default allocation policy for virtual disks created in an enclosure-aware storage pool.
For example, an enclosure-aware subsystem could balance each data copy of the virtual disk across multiple physical enclosures such that each enclosure contains a full data copy of the virtual disk.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -FaultDomainAwarenessDefault
Specifies the default fault domain for new virtual disks created in this storage pool.
The acceptable values for this parameter are:

- PhysicalDisk
- StorageScaleUnit
- StorageChassis
- StorageEnclosure
- StorageRack

The fault domain specifies at what level you want to be fault tolerant.
For example, specify StorageScaleUnit to store data copies on separate nodes of a Storage Spaces Direct cluster.
This cmdlet refers to nodes of a Storage Spaces Direct cluster as storage scale units because you can expand the scale of the cluster by adding more nodes.

```yaml
Type: FaultDomainType
Parameter Sets: (All)
Aliases:
Accepted values: PhysicalDisk, StorageEnclosure, StorageScaleUnit, StorageChassis, StorageRack

Required: False
Position: Named
Default value: PhysicalDisk
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Specifies a friendly name for the storage pool to be created.
The friendly name may be defined by a user and is not guaranteed to be unique.

```yaml
Type: String
Parameter Sets: (All)
Aliases: StoragePoolFriendlyName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LogicalSectorSizeDefault
Specifies the default logical sector size to use for virtual disks created in this pool.
Valid logical sector size values (in bytes) for virtual disks created by using the Windows Storage subsystem are 512 and 4096.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 512
Accept pipeline input: False
Accept wildcard characters: False
```

### -MediaTypeDefault


```yaml
Type: MediaType
Parameter Sets: (All)
Aliases:
Accepted values: HDD, SSD, SCM

Required: False
Position: Named
Default value: Unspecified
Accept pipeline input: False
Accept wildcard characters: False
```

### -OtherUsageDescription
Specifies the usage description for the storage pool.

```yaml
Type: String
Parameter Sets: (All)
Aliases: StoragePoolOtherUsageDescription

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalDisks
Accepts one or more PhysicalDisk objects as input.
The Physical Disk CIM objects represent the physical disks to be added to the storage pool.

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProvisioningTypeDefault
Specifies the default type of provisioning for virtual disks created in this pool.
The acceptable values for this parameter are: Unknown, Fixed or Thin.

```yaml
Type: ProvisioningType
Parameter Sets: (All)
Aliases:
Accepted values: Unknown, Thin, Fixed

Required: False
Position: Named
Default value: Fixed
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResiliencySettingNameDefault
Specifies the default resiliency setting (also known as storage layout) to use for virtual disks created in the specified storage pool. The supported resiliency settings vary by storage subsystem.
For the Windows Storage subsystem, acceptable values are Mirror, Parity, and Simple. "Mirror" is the default value.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Mirror
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageSubSystemFriendlyName
Specifies the friendly name of the storage subsystem on which you want to create the storage pool.

```yaml
Type: String[]
Parameter Sets: ByFriendlyName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageSubSystemName
Specifies the name of the storage subsystem (provided by the Storage Management) on which you want to create the storage pool.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageSubSystemUniqueId
Specifies the ID of the storage subsystem on which you want to create the storage pool

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases: StorageSubsystemId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Usage
Specifies the usage setting for the storage pool.
The acceptable values for this parameter are:
- Other
- ReservedAsDeltaReplicaContainer
- ReservedForComputerSystem
- ReservedForLocalReplicationServices
- ReservedForMigrationServices
- ReservedForRemoteReplicationServices
- ReservedForSparing
- Unrestricted

```yaml
Type: Usage
Parameter Sets: (All)
Aliases: StoragePoolUsage
Accepted values: Other, Unrestricted, ReservedForComputerSystem, ReservedAsDeltaReplicaContainer, ReservedForMigrationServices, ReservedForLocalReplicationServices, ReservedForRemoteReplicationServices, ReservedForSparing

Required: False
Position: Named
Default value: Other
Accept pipeline input: False
Accept wildcard characters: False
```

### -WriteCacheSizeDefault
Specifies the default write-back cache size for virtual disks in the storage pool.

```yaml
Type: UInt64
Parameter Sets: (All)
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
You can use the pipeline operator to pass one or more MSFT_PhysicalDisk objects to the *PhysicalDisks* parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubsystem
You can use the pipeline operator to pass an MSFT_StorageSubsystem object to the *InputObject* parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
This cmdlet returns an object representing the newly created storage pool.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-PhysicalDisk](./Get-PhysicalDisk.md)

[Get-StoragePool](./Get-StoragePool.md)

[New-Volume](./New-Volume.md)

[Remove-StoragePool](./Remove-StoragePool.md)

[Set-StoragePool](./Set-StoragePool.md)
