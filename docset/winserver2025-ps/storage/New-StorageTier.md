---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StoragePool.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/new-storagetier?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-StorageTier
---

# New-StorageTier

## SYNOPSIS
Creates a storage tier.

## SYNTAX

### ByFriendlyName (Default)
```
New-StorageTier [-StoragePoolFriendlyName] <String[]> -FriendlyName <String> [-MediaType <MediaType>]
 [-FaultDomainAwareness <FaultDomainType>] [-ColumnIsolation <FaultDomainType>]
 [-ResiliencySettingName <String>] [-PhysicalDiskRedundancy <UInt16>] [-NumberOfDataCopies <UInt16>]
 [-NumberOfGroups <UInt16>] [-NumberOfColumns <UInt16>] [-Interleave <UInt64>] [-Description <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
New-StorageTier -StoragePoolUniqueId <String[]> -FriendlyName <String> [-MediaType <MediaType>]
 [-FaultDomainAwareness <FaultDomainType>] [-ColumnIsolation <FaultDomainType>]
 [-ResiliencySettingName <String>] [-PhysicalDiskRedundancy <UInt16>] [-NumberOfDataCopies <UInt16>]
 [-NumberOfGroups <UInt16>] [-NumberOfColumns <UInt16>] [-Interleave <UInt64>] [-Description <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByName
```
New-StorageTier -StoragePoolName <String[]> -FriendlyName <String> [-MediaType <MediaType>]
 [-FaultDomainAwareness <FaultDomainType>] [-ColumnIsolation <FaultDomainType>]
 [-ResiliencySettingName <String>] [-PhysicalDiskRedundancy <UInt16>] [-NumberOfDataCopies <UInt16>]
 [-NumberOfGroups <UInt16>] [-NumberOfColumns <UInt16>] [-Interleave <UInt64>] [-Description <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### InputObject (cdxml)
```
New-StorageTier -InputObject <CimInstance[]> -FriendlyName <String> [-MediaType <MediaType>]
 [-FaultDomainAwareness <FaultDomainType>] [-ColumnIsolation <FaultDomainType>]
 [-ResiliencySettingName <String>] [-PhysicalDiskRedundancy <UInt16>] [-NumberOfDataCopies <UInt16>]
 [-NumberOfGroups <UInt16>] [-NumberOfColumns <UInt16>] [-Interleave <UInt64>] [-Description <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **New-StorageTier** cmdlet creates a storage tier in a storage pool.

## EXAMPLES

### Example 1: Create a storage tier
```
PS C:\> New-StorageTier -StoragePoolFriendlyName "TierPool01" -FriendlyName "Tier11" -MediaType HDD
```

This command creates a storage tier for hard disk drives named Tier11 in the storage pool named TierPool01.

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

### -ColumnIsolation
Specifies at which level columns within a virtual disk should be isolated from each other.
We recommend omitting this parameter and using the defaults.
The acceptable values for this parameter are:

- PhysicalDisk
- StorageScaleUnit
- StorageChassis
- StorageEnclosure
- StorageRack

```yaml
Type: FaultDomainType
Parameter Sets: (All)
Aliases:
Accepted values: PhysicalDisk, StorageEnclosure, StorageScaleUnit, StorageChassis, StorageRack

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the storage tier that you create.

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

### -FaultDomainAwareness
Specifies at what level you want the virtual disk to be fault tolerant.
The acceptable values for this parameter are:

- PhysicalDisk
- StorageScaleUnit
- StorageChassis
- StorageEnclosure
- StorageRack

For example, specify StorageScaleUnit to store data copies on separate nodes of a Storage Spaces Direct cluster.
This cmdlet refers to nodes of a Storage Spaces Direct cluster as storage scale units because you can expand the scale of the cluster by adding more nodes.

```yaml
Type: FaultDomainType
Parameter Sets: (All)
Aliases:
Accepted values: PhysicalDisk, StorageEnclosure, StorageScaleUnit, StorageChassis, StorageRack

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Specifies a friendly name for the storage tier.

```yaml
Type: String
Parameter Sets: (All)
Aliases: StorageTierFriendlyName

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

### -Interleave
Specifies the interleave value to use during the creation of a storage tier.
The interleave value represents the number of bytes that is written to a single physical disk.
Thus `Interleave * NumberOfColumns` yields the size of one stripe of user data.

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
Parameter Sets: (All)
Aliases:
Accepted values: HDD, SSD, SCM

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumberOfColumns
Specifies the number of columns to use for the storage tier.
Columns represent the number of underlying physical disks in a tier across which one stripe of data for a virtual disk is written.

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
Specify 2 to create a two-way mirror, or 3 to specify a three-way mirror or for dual-parity.

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

### -NumberOfGroups
Specifics the number of groups used by Local Reconstruction Coding (LRC) with a dual parity virtual disk.
We recommend omitting this parameter and using the defaults.

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

### -PhysicalDiskRedundancy
Specifies the physical disk redundancy value to use during the creation of a virtual disk.
This value represents how many failed physical disks the virtual disk can tolerate without data loss.
The redundancy values are as follows:

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

### -ResiliencySettingName
Specifies the resiliency setting, or storage layout, to use for the virtual disk.
The acceptable values for this parameter are: Simple, Mirror, and Parity.

By default, when you specify Mirror, Storage Spaces creates a two-way mirror.
When you specify Parity, Storage Spaces creates a single-parity space.

To create a three-way mirror space, specify 3 for the *NumberofDataCopies* parameter or 2 for the *PhysicalDiskRedundancy* parameter.

To create a dual-parity space, specify 2 for the *PhysicalDiskRedundancy* parameter and Fixed provisioning for the *ProvisioningType* parameter.

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

### -StoragePoolFriendlyName
Specifies the friendly name of a storage pool.
The cmdlet creates the storage tier in the storage pool that you specify.

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
Specifies the name of a storage pool.
The cmdlet creates the storage tier in the storage pool that you specify.
This human-readable name is not necessarily unique.

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
Specifies the unique ID, as a string, of a storage pool.
The cmdlet creates the storage tiers in the storage pool that has the ID that you specify.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
You can use the pipeline operator to pass a MSFT_StoragePool object to the **InputObject** parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/microsoft/windows/storage/MSFT_StorageTier
This cmdlet outputs an object that represents the storage tier

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-StorageTier](./Get-StorageTier.md)

[Remove-StorageTier](./Remove-StorageTier.md)

[Resize-StorageTier](./Resize-StorageTier.md)

[Set-StorageTier](./Set-StorageTier.md)

