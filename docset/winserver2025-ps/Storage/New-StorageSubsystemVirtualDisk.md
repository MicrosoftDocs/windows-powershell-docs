---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageSubSystem.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/new-storagesubsystemvirtualdisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-StorageSubsystemVirtualDisk
---

# New-StorageSubsystemVirtualDisk

## SYNOPSIS
Allows the creation of a VirtualDisk object on a storage subsystem that does not support creation of storage pools.

## SYNTAX

### ByFriendlyName (Default)
```
New-StorageSubsystemVirtualDisk [-StorageSubSystemFriendlyName] <String[]> [-FriendlyName <String>]
 [-Usage <Usage>] [-OtherUsageDescription <String>] [-Size <UInt64>] [-UseMaximumSize] [-Interleave <UInt64>]
 [-NumberOfColumns <UInt16>] [-PhysicalDiskRedundancy <UInt16>] [-NumberOfDataCopies <UInt16>]
 [-ParityLayout <ParityLayout>] [-RequestNoSinglePointOfFailure <Boolean>]
 [-ProvisioningType <ProvisioningType>] [-IsEnclosureAware] [-FaultDomainAwareness <FaultDomainType>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
New-StorageSubsystemVirtualDisk -StorageSubSystemUniqueId <String[]> [-FriendlyName <String>] [-Usage <Usage>]
 [-OtherUsageDescription <String>] [-Size <UInt64>] [-UseMaximumSize] [-Interleave <UInt64>]
 [-NumberOfColumns <UInt16>] [-PhysicalDiskRedundancy <UInt16>] [-NumberOfDataCopies <UInt16>]
 [-ParityLayout <ParityLayout>] [-RequestNoSinglePointOfFailure <Boolean>]
 [-ProvisioningType <ProvisioningType>] [-IsEnclosureAware] [-FaultDomainAwareness <FaultDomainType>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByName
```
New-StorageSubsystemVirtualDisk -StorageSubSystemName <String[]> [-FriendlyName <String>] [-Usage <Usage>]
 [-OtherUsageDescription <String>] [-Size <UInt64>] [-UseMaximumSize] [-Interleave <UInt64>]
 [-NumberOfColumns <UInt16>] [-PhysicalDiskRedundancy <UInt16>] [-NumberOfDataCopies <UInt16>]
 [-ParityLayout <ParityLayout>] [-RequestNoSinglePointOfFailure <Boolean>]
 [-ProvisioningType <ProvisioningType>] [-IsEnclosureAware] [-FaultDomainAwareness <FaultDomainType>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### InputObject (cdxml)
```
New-StorageSubsystemVirtualDisk -InputObject <CimInstance[]> [-FriendlyName <String>] [-Usage <Usage>]
 [-OtherUsageDescription <String>] [-Size <UInt64>] [-UseMaximumSize] [-Interleave <UInt64>]
 [-NumberOfColumns <UInt16>] [-PhysicalDiskRedundancy <UInt16>] [-NumberOfDataCopies <UInt16>]
 [-ParityLayout <ParityLayout>] [-RequestNoSinglePointOfFailure <Boolean>]
 [-ProvisioningType <ProvisioningType>] [-IsEnclosureAware] [-FaultDomainAwareness <FaultDomainType>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **New-StorageSubsystemVirtualDisk** cmdlet allows the creation of a VirtualDisk object on a storage subsystem that does not support creation of storage pools, or if its storage pool does not support virtual disk creation.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> $stsubsys = (Get-StorageSubsystem)
PS C:\> New-StorageSubsystemVirtualDisk -StorageSubsystemUniqueId $stsubsys.UniqueID -FriendlyName "VirtualDisk01" -Size "5GB" -ProvisioningType Fixed
```

This example creates a Virtual Disk named VirtualDisk01 on the provided StorageSubsystem without the use of a Storage Pool

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

### -FaultDomainAwareness
Specifies the default fault domain for new virtual disks created in this storage pool.
The fault domain specifies at what level you want to be fault tolerant.
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

### -FriendlyName
Specifies a friendly name for a virtual disk.
The friendly name may be defined by a user and is not guaranteed to be unique.

```yaml
Type: String
Parameter Sets: (All)
Aliases: VirtualDiskFriendlyName

Required: False
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
Therefore, `Interleave * NumberOfColumns` yields the size of one stripe of user data.

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
Specifies that the enclosure supports SCSI Enclosure Services (SES), which is utilized for providing things like Slot location for a physical disk, as well as to manage LEDs on the disks for visual identification.

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

### -NumberOfColumns
Specifies the number of columns to create.

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

### -OtherUsageDescription
Specifies the usage of this object.

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

### -ParityLayout
Specifies the parity layout to be used with the virtual disk to be created.

```yaml
Type: ParityLayout
Parameter Sets: (All)
Aliases:
Accepted values: NonRotatedParity, RotatedParity

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalDiskRedundancy
Specifies the physical disk redundancy value to use during the creation of a virtual disk.

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

### -ProvisioningType
Specifies the type of provisioning.
The acceptable values for this parameter are: Unknown, Fixed, or Thin.

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

### -RequestNoSinglePointOfFailure
Requests that the virtual disk is created on hardware that has path redundancy to provide resilience to storage path faults.
This cannot be guaranteed.

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

### -Size
Specifies the size of the partition to create.
If not specified, then the number will default to **Bytes**.
The acceptable values for this parameter are: **Bytes**, **KB**, **MB**, **GB**, or **TB**.
The size may be defined by a user.

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

### -StorageSubSystemFriendlyName
Specifies the friendly name of the storage subsystem.
The friendly name may be defined by the user.

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
Specifies the name of the storage subsystem provided by the Storage Management.

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
Specifies an ID used to uniquely identify the storage subsystem in the system.
The ID persists through reboots.

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
Specifies the intended usage.

```yaml
Type: Usage
Parameter Sets: (All)
Aliases:
Accepted values: Other, Unrestricted, ReservedForComputerSystem, ReservedForReplicationServices, ReservedForMigrationServices, LocalReplicaSource, RemoteReplicaSource, LocalReplicaTarget, RemoteReplicaTarget, LocalReplicaSourceOrTarget, RemoteReplicaSourceOrTarget, DeltaReplicaTarget, ElementComponent, ReservedAsPoolContributer, CompositeVolumeMember, CompositeVirtualDiskMember, ReservedForSparing

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseMaximumSize
Uses the maximum allowable size for this virtual disk.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubsystem
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

