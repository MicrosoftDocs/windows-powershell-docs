---
author: Kateyanne
description: 
external help file: StorageCmdlets.cdxml-help.xml
manager: jasgro
Module Name: Storage
ms.author: v-kaunu
ms.date: 10/29/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/storage/set-storagepool?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-StoragePool
---

# Set-StoragePool

## SYNOPSIS
Modifies the properties of the specified storage pool.

## SYNTAX

### ByUniqueId (Default)
```
Set-StoragePool [-NewFriendlyName <String>] [-ClearOnDeallocate <Boolean>] [-IsPowerProtected <Boolean>]
 [-RepairPolicy <RepairPolicy>] [-RetireMissingPhysicalDisks <RetireMissingPhysicalDisks>] [-Usage <Usage>]
 [-OtherUsageDescription <String>] [-ThinProvisioningAlertThresholds <UInt16[]>] -UniqueId <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectAttributes
```
Set-StoragePool [-InputObject] <CimInstance[]> [-IsReadOnly <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectDefaults
```
Set-StoragePool [-InputObject] <CimInstance[]> [-ProvisioningTypeDefault <ProvisioningType>]
 [-ResiliencySettingNameDefault <String>] [-EnclosureAwareDefault <Boolean>] [-WriteCacheSizeDefault <UInt64>]
 [-AutoWriteCacheSize <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByObject
```
Set-StoragePool [-InputObject] <CimInstance[]> [-NewFriendlyName <String>] [-ClearOnDeallocate <Boolean>]
 [-IsPowerProtected <Boolean>] [-RepairPolicy <RepairPolicy>]
 [-RetireMissingPhysicalDisks <RetireMissingPhysicalDisks>] [-Usage <Usage>] [-OtherUsageDescription <String>]
 [-ThinProvisioningAlertThresholds <UInt16[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByFriendlyName
```
Set-StoragePool [-NewFriendlyName <String>] [-ClearOnDeallocate <Boolean>] [-IsPowerProtected <Boolean>]
 [-RepairPolicy <RepairPolicy>] [-RetireMissingPhysicalDisks <RetireMissingPhysicalDisks>] [-Usage <Usage>]
 [-OtherUsageDescription <String>] [-ThinProvisioningAlertThresholds <UInt16[]>] [-FriendlyName] <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByName
```
Set-StoragePool [-NewFriendlyName <String>] [-ClearOnDeallocate <Boolean>] [-IsPowerProtected <Boolean>]
 [-RepairPolicy <RepairPolicy>] [-RetireMissingPhysicalDisks <RetireMissingPhysicalDisks>] [-Usage <Usage>]
 [-OtherUsageDescription <String>] [-ThinProvisioningAlertThresholds <UInt16[]>] -Name <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueIdAttributes
```
Set-StoragePool -UniqueId <String> [-IsReadOnly <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueIdDefaults
```
Set-StoragePool -UniqueId <String> [-ProvisioningTypeDefault <ProvisioningType>]
 [-ResiliencySettingNameDefault <String>] [-EnclosureAwareDefault <Boolean>] [-WriteCacheSizeDefault <UInt64>]
 [-AutoWriteCacheSize <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByNameAttributes
```
Set-StoragePool -Name <String> [-IsReadOnly <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByNameDefaults
```
Set-StoragePool -Name <String> [-ProvisioningTypeDefault <ProvisioningType>]
 [-ResiliencySettingNameDefault <String>] [-EnclosureAwareDefault <Boolean>] [-WriteCacheSizeDefault <UInt64>]
 [-AutoWriteCacheSize <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByFriendlyNameAttributes
```
Set-StoragePool [-FriendlyName] <String> [-IsReadOnly <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByFriendlyNameDefaults
```
Set-StoragePool [-FriendlyName] <String> [-ProvisioningTypeDefault <ProvisioningType>]
 [-ResiliencySettingNameDefault <String>] [-EnclosureAwareDefault <Boolean>] [-WriteCacheSizeDefault <UInt64>]
 [-AutoWriteCacheSize <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-StoragePool** cmdlet modifies the properties of the specified storage pool.

## EXAMPLES

### Example 1: Change the friendly name
```
PS C:\>Set-StoragePool -FriendlyName StoragePool -NewFriendlyName StoragePool2
```

This example changes the friendly name of StoragePool to StoragePool2.

### Example 2: Make a read-only storage pool writeable
```
PS C:\>Set-StoragePool -FriendlyName "Storage Pool 1" -IsReadOnly $False
```

This example makes the storage pool named Storage Pool 1 writable when it is in a read-only state.

### Example 3: Set the default resiliency and provisioning settings
```
PS C:\>Set-StoragePool -FriendlyName "Storage Pool 1" -ResiliencySettingsNameDefault Mirror -ProvisioningTypeDefault Thin
```

This example makes any new virtual disks by default use the Mirror resiliency setting and thin provisioning.

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

### -AutoWriteCacheSize
Indicates whether to set the size of the write-back cache to 1 GB for all types of storage spaces, which include simple, mirror, and parity, to create from the pool.
If the number or size of the solid-state drives (SSDs) or journal disks in the storage pool is not sufficient and you specify a value of $True for this parameter, the cmdlet sets the write-back cache size to 0 for simple and mirror spaces, and to 32 MB for parity spaces.

```yaml
Type: Boolean
Parameter Sets: ByObjectDefaults, ByUniqueIdDefaults, ByNameDefaults, ByFriendlyNameDefaults
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

### -ClearOnDeallocate
Clears all blocks on the physical disks in the storage pool upon deallocation.
Clearing all blocks is more secure, but is much slower to deallocate.

```yaml
Type: Boolean
Parameter Sets: ByUniqueId, ByObject, ByFriendlyName, ByName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnclosureAwareDefault
Specifies that the storage pool should use enclosure awareness by default when creating storage spaces.

To support deployments that require an added level of fault tolerance, Storage Spaces can associate each copy of data with a particular just-a-bunch-of-disk (JBOD) enclosure.
This capability is known as enclosure awareness.
With enclosure awareness, if one enclosure fails or goes offline, the data remains available in one or more alternate enclosures.

To use enclosure awareness, you must use JBODs that are certified for use with Storage Spaces and you must have a sufficient number of JBODs and disks to support the resiliency types of the storage spaces you create (generally you'll need three or four JBODs).
For a list of certified JBODs, see the Windows Server Cataloghttp://windowsservercatalog.com/results.aspx?&chtext=&cstext=&csttext=&chbtext=&bCatID=1645&cpID=0&avc=10&ava=0&avq=0&OR=1&PGS=25&ready=0.
For more information about enclosure awareness, see Storage Spaces Frequently Asked Questionshttp://social.technet.microsoft.com/wiki/contents/articles/11382.storage-spaces-frequently-asked-questions-faq.aspx.

```yaml
Type: Boolean
Parameter Sets: ByObjectDefaults, ByUniqueIdDefaults, ByNameDefaults, ByFriendlyNameDefaults
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Specifies the friendly name of the storage pool on which you want to set attributes.

```yaml
Type: String
Parameter Sets: ByFriendlyName, ByFriendlyNameAttributes, ByFriendlyNameDefaults
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Accepts an array of storage pool objects from the pipeline as input.

```yaml
Type: CimInstance[]
Parameter Sets: ByObjectAttributes, ByObjectDefaults, ByObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IsPowerProtected
Indicates whether the physical disks that belong to the storage pool have backup power systems, such as battery backup.
If you specify a value of $True for this parameter, the storage pool does not perform flush operations, and the pool removes write-through attributes from commands.

```yaml
Type: Boolean
Parameter Sets: ByUniqueId, ByObject, ByFriendlyName, ByName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsReadOnly
Sets the object to be read-only (`IsReadOnly $true`) or read-write (`IsReadOnly $false`).
**Note**: If the object is set to read-only (`IsReadOnly $true`), the object must be set to read-write (`IsReadOnly $false`) before using this cmdlet to set the **PartitionStyle** parameter.

```yaml
Type: Boolean
Parameter Sets: ByObjectAttributes, ByUniqueIdAttributes, ByNameAttributes, ByFriendlyNameAttributes
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the storage pool on which you want to set attributes.

```yaml
Type: String
Parameter Sets: ByName, ByNameAttributes, ByNameDefaults
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NewFriendlyName
Specifies the new friendly name for the storage pool.

```yaml
Type: String
Parameter Sets: ByUniqueId, ByObject, ByFriendlyName, ByName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OtherUsageDescription
Specifies the OtherUsageDescription for the storage pool.

```yaml
Type: String
Parameter Sets: ByUniqueId, ByObject, ByFriendlyName, ByName
Aliases: NewOtherUsageDescription

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProvisioningTypeDefault
Specifies the default type of provisioning to use for virtual disks created in the specified storage pool.
The acceptable values for this parameter are: **Fixed** or **Thin**.

```yaml
Type: ProvisioningType
Parameter Sets: ByObjectDefaults, ByUniqueIdDefaults, ByNameDefaults, ByFriendlyNameDefaults
Aliases: 
Accepted values: Unknown, Thin, Fixed

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RepairPolicy
Specifies how the operating system proceeds with repairing virtual disks in the specified storage pool.
The acceptable values for this parameter are:
--**Sequential** Repair processes one allocation slab at a time.
Specifying this value results in longer repair times, but smaller impact on I/O load. 
--**Parallel** Repair processes as many allocation slabs as it can in parallel.  Specifying this value results in the shortest repair time, but significantly impacts I/O load.

```yaml
Type: RepairPolicy
Parameter Sets: ByUniqueId, ByObject, ByFriendlyName, ByName
Aliases: 
Accepted values: Sequential, Parallel

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResiliencySettingNameDefault
Specifies the default resiliency setting (also known as storage layout) to use for virtual disks the created in the specified storage pool.
The supported resiliency settings vary by storage subsystem.
Acceptable values for the Storage Spaces subsystem are Mirror, Parity, and Simple.

```yaml
Type: String
Parameter Sets: ByObjectDefaults, ByUniqueIdDefaults, ByNameDefaults, ByFriendlyNameDefaults
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetireMissingPhysicalDisks
Specifies when Windows should set the Usage property of physical disks missing from a storage pool to Retired.
The acceptable values for this parameter are:
-**Auto** This is the default setting for storage pools.
When set to **Auto**, Windows retires missing disks, but doesn't automatically rebuild affected virtual disks unless there are physical disks whose Usage value is set to **HotSpare**, in which case Windows rebuilds the virtual disks five minutes after the failed write operation. 
-**Always** This is the recommended setting when using free pool space to rebuild storage spaces instead of using hot-spare disks.
When set to **Always**, Windows retires missing physical disks and automatically rebuilds affected virtual disks five minutes after the failed write operation.
-**Never** When set to **Never**, Windows never retires missing physical disks.

```yaml
Type: RetireMissingPhysicalDisks
Parameter Sets: ByUniqueId, ByObject, ByFriendlyName, ByName
Aliases: 
Accepted values: Auto, Always, Never

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThinProvisioningAlertThresholds
Specifies how full a storage pool must get (in percent) before an alert is generated to add physical disks to the storage pool to support thinly provisioned virtual disks.

```yaml
Type: UInt16[]
Parameter Sets: ByUniqueId, ByObject, ByFriendlyName, ByName
Aliases: 

Required: False
Position: Named
Default value: 70
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

### -UniqueId
Specifies the UniqueID of the storage pool for which you want to set attributes.

```yaml
Type: String
Parameter Sets: ByUniqueId, ByUniqueIdAttributes, ByUniqueIdDefaults
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Usage
Specifies the usage setting for the storage pool.
The acceptable values for this parameter are:Other, ReservedAsDeltaReplicaContainer, ReservedForComputerSystem, ReservedForLocalReplicationServices, ReservedForMigrationServices, ReservedForRemoteReplicationServices, ReservedForSparing, and Unrestricted.

```yaml
Type: Usage
Parameter Sets: ByUniqueId, ByObject, ByFriendlyName, ByName
Aliases: NewUsage
Accepted values: Other, Unrestricted, ReservedForComputerSystem, ReservedAsDeltaReplicaContainer, ReservedForMigrationServices, ReservedForLocalReplicationServices, ReservedForRemoteReplicationServices, ReservedForSparing

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WriteCacheSizeDefault
Specifies the default write-back cache size for virtual disks in the storage pool.

```yaml
Type: UInt64
Parameter Sets: ByObjectDefaults, ByUniqueIdDefaults, ByNameDefaults, ByFriendlyNameDefaults
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
You can use the pipeline operator to pass one or more MSFT_StoragePool objects to the InputObject parameter.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-StoragePool](./Get-StoragePool.md)

[New-StoragePool](./New-StoragePool.md)

[Remove-StoragePool](./Remove-StoragePool.md)

