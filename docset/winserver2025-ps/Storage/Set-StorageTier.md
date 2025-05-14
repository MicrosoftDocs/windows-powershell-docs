---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageCmdlets.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/set-storagetier?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-StorageTier
---

# Set-StorageTier

## SYNOPSIS
Modifies a storage tier.

## SYNTAX

### ByUniqueIdNewFriendlyName (Default)
```
Set-StorageTier [-NewFriendlyName <String>] -UniqueId <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectDescription
```
Set-StorageTier -InputObject <CimInstance[]> [-Description <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectAttributes
```
Set-StorageTier -InputObject <CimInstance[]> [-MediaType <MediaType>] [-FaultDomainAwareness <FaultDomainType>]
 [-ColumnIsolation <FaultDomainType>] [-ResiliencySettingName <String>] [-PhysicalDiskRedundancy <UInt16>]
 [-NumberOfDataCopies <UInt16>] [-NumberOfGroups <UInt16>] [-NumberOfColumns <UInt16>] [-Interleave <UInt64>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectNewFriendlyName
```
Set-StorageTier -InputObject <CimInstance[]> [-NewFriendlyName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByFriendlyNameNewFriendlyName
```
Set-StorageTier [-NewFriendlyName <String>] [-FriendlyName] <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByFriendlyNameAttributes
```
Set-StorageTier [-MediaType <MediaType>] [-FaultDomainAwareness <FaultDomainType>]
 [-ColumnIsolation <FaultDomainType>] [-ResiliencySettingName <String>] [-PhysicalDiskRedundancy <UInt16>]
 [-NumberOfDataCopies <UInt16>] [-NumberOfGroups <UInt16>] [-NumberOfColumns <UInt16>] [-Interleave <UInt64>]
 [-FriendlyName] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueIdAttributes
```
Set-StorageTier [-MediaType <MediaType>] [-FaultDomainAwareness <FaultDomainType>]
 [-ColumnIsolation <FaultDomainType>] [-ResiliencySettingName <String>] [-PhysicalDiskRedundancy <UInt16>]
 [-NumberOfDataCopies <UInt16>] [-NumberOfGroups <UInt16>] [-NumberOfColumns <UInt16>] [-Interleave <UInt64>]
 -UniqueId <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByFriendlyNameDescription
```
Set-StorageTier [-Description <String>] [-FriendlyName] <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueIdDescription
```
Set-StorageTier [-Description <String>] -UniqueId <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Set-StorageTier** cmdlet modifies a storage tier.
Use this cmdlet to change the name and description of a storage tier, and to change the media type that is associated with storage tier.

## EXAMPLES

### Example 1: Change the name of a storage tier
```
PS C:\> Set-StorageTier -UniqueId '{49dde1c4-5c34-11e2-8441-00155de88701}' -NewFriendlyName "FastTier"
```

This command changes the friendly name of the storage tier that has the specified ID.

### Example 2: Change the description of a storage tier
```
PS C:\> Get-StorageTier -FriendlyName "FastTier" | Set-StorageTier -Description "This tier denotes fast media in the system"
```

This command uses the Get-StorageTier cmdlet to get the storage tier named FastTier, and then passes the storage tier to the Set-StorageTier cmdlet by using the pipeline operator.
The **Set-StorageTier** cmdlet changes the description of the storage tier to the specified string.

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
Parameter Sets: ByObjectAttributes, ByFriendlyNameAttributes, ByUniqueIdAttributes
Aliases:
Accepted values: PhysicalDisk, StorageEnclosure, StorageScaleUnit, StorageChassis, StorageRack

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the storage tier.

```yaml
Type: String
Parameter Sets: ByObjectDescription, ByFriendlyNameDescription, ByUniqueIdDescription
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FaultDomainAwareness
Specifies at what level you want the storage tier to be fault tolerant.
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
Parameter Sets: ByObjectAttributes, ByFriendlyNameAttributes, ByUniqueIdAttributes
Aliases:
Accepted values: PhysicalDisk, StorageEnclosure, StorageScaleUnit, StorageChassis, StorageRack

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Specifies the friendly name of the storage tier to modify.

```yaml
Type: String
Parameter Sets: ByFriendlyNameNewFriendlyName, ByFriendlyNameAttributes, ByFriendlyNameDescription
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: ByObjectDescription, ByObjectAttributes, ByObjectNewFriendlyName
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
Therefore, `Interleave * NumberOfColumns` yields the size of one stripe of user data.

```yaml
Type: UInt64
Parameter Sets: ByObjectAttributes, ByFriendlyNameAttributes, ByUniqueIdAttributes
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MediaType
Specifies the media type of the storage tier.
The acceptable values for this parameter are:

- SSD
- SCM
- HDD

Use SCM for storage-class memory such as NVDIMMs.

```yaml
Type: MediaType
Parameter Sets: ByObjectAttributes, ByFriendlyNameAttributes, ByUniqueIdAttributes
Aliases:
Accepted values: HDD, SSD, SCM

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewFriendlyName
Specifies a new friendly name for the storage tier.

```yaml
Type: String
Parameter Sets: ByUniqueIdNewFriendlyName, ByObjectNewFriendlyName, ByFriendlyNameNewFriendlyName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumberOfColumns
Specifies the number of columns to use when allocating the storage tier.

```yaml
Type: UInt16
Parameter Sets: ByObjectAttributes, ByFriendlyNameAttributes, ByUniqueIdAttributes
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
Parameter Sets: ByObjectAttributes, ByFriendlyNameAttributes, ByUniqueIdAttributes
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
Parameter Sets: ByObjectAttributes, ByFriendlyNameAttributes, ByUniqueIdAttributes
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
Parameter Sets: ByObjectAttributes, ByFriendlyNameAttributes, ByUniqueIdAttributes
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResiliencySettingName
Specifies the resiliency setting, or storage layout, to use for the virtual disk.
Acceptable values vary by storage subsystem.

Allowed values for the Windows Storage subsystem are: Simple, Mirror, or Parity.
By default, when you specify Mirror, Storage Spaces creates a two-way mirror, and when you specify Parity, Storage Spaces creates a single-parity space.

To create a three-way mirror space, specify 3 for the *NumberofDataCopies* parameter or 2 for the PhysicalDiskRedundancy parameter.

To create a dual-parity space, specify 2 for the *PhysicalDiskRedundancy* parameter and Fixed provisioning for the *ProvisioningType* parameter.

```yaml
Type: String
Parameter Sets: ByObjectAttributes, ByFriendlyNameAttributes, ByUniqueIdAttributes
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

### -UniqueId
Specifies the unique ID of the storage tier to modify.

```yaml
Type: String
Parameter Sets: ByUniqueIdNewFriendlyName, ByUniqueIdAttributes, ByUniqueIdDescription
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubsystem
You can use the pipeline operator to pass an array of MSFT_StorageTier objects to the *InputObject* parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageTier
This cmdlet returns an MSFT_StorageTier object that contains details about the tier such as tier friendly name, media type and size.

## NOTES
* The **Microsoft.Management.Infrastructure.CimInstance** object is a wrapper class that displays Windows Management Instrumentation (WMI) objects. The path after the pound sign (#) provides the namespace and class name for the underlying WMI object.
* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-StorageTier](./Get-StorageTier.md)

[Get-VirtualDisk](./Get-VirtualDisk.md)

[New-StorageTier](./New-StorageTier.md)

[Remove-StorageTier](./Remove-StorageTier.md)

[Resize-StorageTier](./Resize-StorageTier.md)

