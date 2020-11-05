---
external help file: StoragePool.cdxml-help.xml
Module Name: Storage
online version: 
schema: 2.0.0
title: New-VirtualDisk
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 0A351B38-1E4B-451C-A66B-EF97683646F4
ms.author: v-kaunu
ms.reviewer: brianlic
---

# New-VirtualDisk

## SYNOPSIS
Creates a new virtual disk in the specified storage pool.

## SYNTAX

### ByFriendlyName (Default)
```
New-VirtualDisk [-StoragePoolFriendlyName] <String[]> -FriendlyName <String> [-Usage <Usage>]
 [-OtherUsageDescription <String>] [-ResiliencySettingName <String>] [-Size <UInt64>] [-UseMaximumSize]
 [-ProvisioningType <ProvisioningType>] [-IsEnclosureAware <Boolean>] [-PhysicalDisksToUse <CimInstance[]>]
 [-NumberOfDataCopies <UInt16>] [-PhysicalDiskRedundancy <UInt16>] [-NumberOfColumns <UInt16>]
 [-AutoNumberOfColumns] [-Interleave <UInt64>] [-StorageTiers <CimInstance[]>] [-StorageTierSizes <UInt64[]>]
 [-WriteCacheSize <UInt64>] [-AutoWriteCacheSize] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
New-VirtualDisk -StoragePoolUniqueId <String[]> -FriendlyName <String> [-Usage <Usage>]
 [-OtherUsageDescription <String>] [-ResiliencySettingName <String>] [-Size <UInt64>] [-UseMaximumSize]
 [-ProvisioningType <ProvisioningType>] [-IsEnclosureAware <Boolean>] [-PhysicalDisksToUse <CimInstance[]>]
 [-NumberOfDataCopies <UInt16>] [-PhysicalDiskRedundancy <UInt16>] [-NumberOfColumns <UInt16>]
 [-AutoNumberOfColumns] [-Interleave <UInt64>] [-StorageTiers <CimInstance[]>] [-StorageTierSizes <UInt64[]>]
 [-WriteCacheSize <UInt64>] [-AutoWriteCacheSize] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByName
```
New-VirtualDisk -StoragePoolName <String[]> -FriendlyName <String> [-Usage <Usage>]
 [-OtherUsageDescription <String>] [-ResiliencySettingName <String>] [-Size <UInt64>] [-UseMaximumSize]
 [-ProvisioningType <ProvisioningType>] [-IsEnclosureAware <Boolean>] [-PhysicalDisksToUse <CimInstance[]>]
 [-NumberOfDataCopies <UInt16>] [-PhysicalDiskRedundancy <UInt16>] [-NumberOfColumns <UInt16>]
 [-AutoNumberOfColumns] [-Interleave <UInt64>] [-StorageTiers <CimInstance[]>] [-StorageTierSizes <UInt64[]>]
 [-WriteCacheSize <UInt64>] [-AutoWriteCacheSize] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### InputObject (cdxml)
```
New-VirtualDisk -InputObject <CimInstance[]> -FriendlyName <String> [-Usage <Usage>]
 [-OtherUsageDescription <String>] [-ResiliencySettingName <String>] [-Size <UInt64>] [-UseMaximumSize]
 [-ProvisioningType <ProvisioningType>] [-IsEnclosureAware <Boolean>] [-PhysicalDisksToUse <CimInstance[]>]
 [-NumberOfDataCopies <UInt16>] [-PhysicalDiskRedundancy <UInt16>] [-NumberOfColumns <UInt16>]
 [-AutoNumberOfColumns] [-Interleave <UInt64>] [-StorageTiers <CimInstance[]>] [-StorageTierSizes <UInt64[]>]
 [-WriteCacheSize <UInt64>] [-AutoWriteCacheSize] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **New-VirtualDisk** cmdlet creates a new virtual disk in the specified storage pool.

## EXAMPLES

### Example 1: Creating a 100 GB virtual disk using default settings
```
PS C:\> New-VirtualDisk -StoragePoolFriendlyName CompanyData -FriendlyName UserData -Size 100GB
```

This example creates a virtual disk named UserData from the storage pool named CompanyData that is 100GB in size, using the storage pool default settings for unspecified parameters.

### Example 2: Creating a thinly-provisioned mirror
```
PS C:\> New-VirtualDisk -StoragePoolFriendlyName CompanyData -FriendlyName DataWarehouse -ResiliencySettingName Mirror -Size 42TB -ProvisioningType Thin
```

This example creates a virtual disk named DataWarehouse, which is 42TB in size, uses the Mirror resiliency setting, and is thinly provisioned.

### Example 3: Creating a three-way mirror
```
PS C:\> New-VirtualDisk -StoragePoolFriendlyName CompanyData -FriendlyName BusinessCritical -ResiliencySettingName Mirror -NumberOfDataCopies 3 -Size 42TB -ProvisioningType Thin
```

This example creates a 42 TB thinly-provisioned virtual disk on the Storage Spaces subsystem, using the Mirror resiliency setting with three data copies.
This creates a three-way mirror that is capable of tolerating two disk failures).

### Example 4: Creating a two-column mirror
```
PS C:\> New-VirtualDisk -StoragePoolFriendlyName CompanyData -FriendlyName BusinessCritical -ResiliencySettingName Mirror - -Size 42TB -ProvisioningType Thin -NumberOfColumns 2
```

This example creates a thinly-provisioned virtual disk on the Storage Spaces subsystem that uses two columns, regardless of how many physical disks are in the storage pool above the two-disk minimum for a two-way mirror.

### Example 5: Create a mirror space with storage tiers
```
PS C:\> $SSD = Get-StorageTier -FriendlyName *SSD*
PS C:\> $HDD = Get-StorageTier -FriendlyName *HDD*
PS C:\> Get-StoragePool CompanyData | New-VirtualDisk -FriendlyName "UserData01" -ResiliencySettingName "Mirror" -StorageTiers $SSD, $HDD -StorageTierSizes 8GB, 32GB
```

This example creates a 40 GB fixed provisioning virtual disk on the Storage Spaces subsystem.
The virtual disk uses the Mirror resiliency setting and storage tiers to store 8 GB of data on the SSD tier and 32 GB of data on the HDD tier.

### Example 6: Create a dual-parity space
```
PS C:\>New-VirtualDisk -StoragePoolFriendlyName "CompanyData" -FriendlyName "ArchivalData" -Size 50GB -ProvisioningType Fixed -ResiliencySettingName "Parity" -PhysicalDiskRedundancy 2
```

This example creates a virtual disk on the Storage Spaces subsystem that uses the dual-parity resiliency type to help protect against two simultaneous disk failures and maximize capacity efficiency.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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

### -AutoNumberOfColumns
Specifies that the number of columns used by the virtual disk should be automatically determined.
Columns represent the number of underlying physical disks across which one stripe of data for a virtual disk is written.

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
Indicates that the cmdlet sets the size of the write-back cache to 1 GB for all types of storage spaces, which include simple, mirror, and parity, to create from the pool.
If the number or size of the solid-state drives (SSDs) or journal disks in the storage pool is not sufficient and you specify a value of $True for this parameter, the cmdlet sets the write-back cache size to 0 for simple and mirror spaces, and to 32 MB for parity spaces.

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -FriendlyName
Specifies the friendly name for the virtual disk.
The friendly name is not required to be unique.

```yaml
Type: String
Parameter Sets: (All)
Aliases: VirtualDiskFriendlyName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Accepts a StoragePool object as input, specifying in which storage pool to create the virtual disk.

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

### -Interleave
Specifies the interleave value to use during the creation of a virtual disk.
The interleave value represents the number of bytes that is written to a single physical disk.
Thus Interleave * NumberOfColumns will yield the size of one stripe of user data.

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

### -IsEnclosureAware
Specifies that the virtual disk should use enclosure awareness.

To support deployments that require an added level of fault tolerance, Storage Spaces can associate each copy of data with a particular just-a-bunch-of-disk (JBOD) enclosure.
This capability is known as enclosure awareness.
With enclosure awareness, if one enclosure fails or goes offline, the data remains available in one or more alternate enclosures.

To use enclosure awareness, you must use JBODs that are certified for use with Storage Spaces and you must have a sufficient number of JBODs and disks to support the resiliency types of the storage spaces you create (generally you'll need three or four JBODs).
For a list of certified JBODs, see the Windows Server Cataloghttp://windowsservercatalog.com/results.aspx?&chtext=&cstext=&csttext=&chbtext=&bCatID=1645&cpID=0&avc=10&ava=0&avq=0&OR=1&PGS=25&ready=0.
For more information about enclosure awareness, see Storage Spaces Frequently Asked Questionshttp://social.technet.microsoft.com/wiki/contents/articles/11382.storage-spaces-frequently-asked-questions-faq.aspx.

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

### -NumberOfColumns
Specifies the number of columns to use when allocating the virtual disk.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumberOfDataCopies
Specifies the number of data copies to create.
Specify 2 to create a two-way mirror, or 3 to specify a three-way mirror.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 1
Accept pipeline input: False
Accept wildcard characters: False
```

### -OtherUsageDescription
Specifies an OtherUsageDescription string for the virtual disk.
You can use the **OtherUsageDescription** parameter only if you set the **Usage** parameter to Other or do not include the **Usage** parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: VirtualDiskOtherUsageDescription

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalDiskRedundancy
Specifies the physical disk redundancy value to use during the creation of a virtual disk.
This value represents how many failed physical disks the virtual disk can tolerate without data loss. 

- For two-way mirror spaces, the virtual disk can tolerate 1 failed physical disk without data loss. 
- For three-way mirror spaces, the virtual disk can tolerate 2 failed physical disks without data loss. 
- For single-parity spaces, the virtual disk can tolerate 1 failed physical disk without data loss. 
- For dual-parity spaces the virtual disk can tolerate 2 failed physical disks without data loss.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalDisksToUse
Specifies an array of one or more PhysicalDisk objects.
The PhysicalDisk objects represent the specific physical disks on which to create this virtual disk.

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProvisioningType
Specifies the type of provisioning.
The acceptable values for this parameter are:**Fixed**, or **Thin**.
You must specify Fixed for storage spaces that use storage tiers or a clustered storage pool.

```yaml
Type: ProvisioningType
Parameter Sets: (All)
Aliases: 
Accepted values: Unknown, Thin, Fixed

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResiliencySettingName
Specifies the resiliency setting (storage layout) to use for the virtual disk.
Acceptable values vary by storage subsystem.

Allowed values for the Storage Spaces subsystem are: **Simple**, **Mirror**, or **Parity**.
By default, when you specify Mirror, Storage Spaces creates a two-way mirror, and when you specify Parity, Storage Spaces creates a single-parity space.

To create a three-way mirror space, specify 3 for the **NumberofDataCopies** parameter or 2 for the **PhysicalDiskRedundancy** parameter.

To create a dual-parity space, specify 2 for the **PhysicalDiskRedundancy** parameter and Fixed provisioning for the **ProvisioningType** parameter.

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

### -Size
Specifies the size of the virtual disk to create.
The default unit is Bytes; to specify a different unit, enter the size followed by one of the following unit values, with no spaces: Bytes, KB, MB, GB, or TB.

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

### -StoragePoolFriendlyName
Specifies the friendly name of the storage pool in which to create the virtual disk.
Enter a friendly name, or use wildcard characters to enter a name pattern.

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

### -StoragePoolName
Specifies the name of the storage pool in which to create the virtual disk.
Enter the name of the storage pool provided by the Storage Management Provider, or use wildcard characters to enter a name pattern.

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

### -StoragePoolUniqueId
Specifies the ID of the storage pool in which to create the virtual disk Enter an ID or use wildcard characters to enter a pattern.

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases: StoragePoolId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageTierSizes
Specifies an array of sizes of the storage tiers that you specify for the **StorageTiers** parameter.

```yaml
Type: UInt64[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageTiers
Specifies an array of storage tiers as a **CIMInstance** object.
The cmdlet adds the storage tiers that you specify to the virtual disk.
To obtain a virtual disk object, use the Get-StorageTier cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: (All)
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

### -Usage
Specifies the intended usage of the virtual disk.
You can specify one of the predefined descriptions, or use the default value (Other) and instead use the OtherUsageDescription parameter to specify a custom value.

```yaml
Type: Usage
Parameter Sets: (All)
Aliases: 
Accepted values: Other, Unrestricted, ReservedForComputerSystem, ReservedForReplicationServices, ReservedForMigrationServices, LocalReplicaSource, RemoteReplicaSource, LocalReplicaTarget, RemoteReplicaTarget, LocalReplicaSourceOrTarget, RemoteReplicaSourceOrTarget, DeltaReplicaTarget, ElementComponent, ReservedAsPoolContributer, CompositeVolumeMember, CompositeVirtualDiskMember, ReservedForSparing

Required: False
Position: Named
Default value: Other
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseMaximumSize
Creates a virtual disk with the maximum size possible given the available storage pool space and specified parameters.

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

### -WriteCacheSize
Specifies the size of the write-back cache.
The cmdlet creates the write-back cache of the size that you specify when the cmdlet creates the virtual disk space.

The following describes the behavior of this parameter based on the value that you specify: 

1. If you do not specify this parameter, the cmdlet sets the value of the **WriteCacheSizeDefault** property from the storage pool. 

1. The default setting of **WriteCacheSizeDefault** for a storage pool is Auto, which specifies that Windows Server® 2012 R2 automatically selects the optimal write-back cache size for your configuration.
You can change the value of **WriteCacheSizeDefault** to a concrete value at any time. 

1. The Auto setting for **WriteCacheSize** functions as follows: 
    1. If any of the following is true, Auto is set to 1 GB: 
        1. The storage pool contains at least N drives with enough capacity and you set the **Usage** parameter to Journal.
        (N = 1 for simple spaces, N = 2 for two-way mirror and single parity, N = 3 for three-way mirror and dual parity) 
        1. The storage pool contains at least N drives with enough capacity and the media type of the virtual disk is set to SSD (N = 1 for simple spaces, N = 2 for two-way mirror and single parity, N = 3 for three-way mirror and dual parity) 
    1. Otherwise, Auto is set to 0 (no log) for simple and mirror spaces, and 32 MB for parity spaces.

1. If you specify Auto or 0 (zero) for this parameter and the storage space is not a parity space, the cmdlet verifies that either 3.a.i or 3.a.ii is true.
If either 3.a.i or 3.a.ii is not true, you cannot set **WriteCacheSize** to Auto or 0. 
    1. The objective of these conditions is to help you avoid scenarios in which you force the creation of a write-back cache in situations that result in slower performance.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
You can use the pipeline operator to pass an MSFT_StoragePool object to the InputObject parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageTier
You can use the pipeline operator to pass an array of MSFT_StorageTier objects to the **StorageTiers** parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
The New-VirtualDisk cmdlet returns an object that represents the newly created virtual disk.

## NOTES

## RELATED LINKS

[Add-VirtualDiskToMaskingSet](./Add-VirtualDiskToMaskingSet.md)

[Connect-VirtualDisk](./Connect-VirtualDisk.md)

[Disconnect-VirtualDisk](./Disconnect-VirtualDisk.md)

[Get-StoragePool](./Get-StoragePool.md)

[Get-StorageTier](./Get-StorageTier.md)

[Get-VirtualDisk](./Get-VirtualDisk.md)

[Hide-VirtualDisk](./Hide-VirtualDisk.md)

[New-MaskingSet](./New-MaskingSet.md)

[Remove-VirtualDisk](./Remove-VirtualDisk.md)

[Repair-VirtualDisk](./Repair-VirtualDisk.md)

[Resize-VirtualDisk](./Resize-VirtualDisk.md)

[Set-VirtualDisk](./Set-VirtualDisk.md)

[Show-VirtualDisk](./Show-VirtualDisk.md)

