---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: VirtualDisk.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-virtualdisk?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VirtualDisk
---

# Get-VirtualDisk

## SYNOPSIS
Returns a list of VirtualDisk objects, across all storage pools, across all providers, or optionally a filtered subset based on provided criteria.

## SYNTAX

### ByFriendlyName (Default)
```
Get-VirtualDisk [[-FriendlyName] <String[]>] [-Usage <Usage[]>] [-OtherUsageDescription <String[]>]
 [-IsSnapshot <Boolean[]>] [-HealthStatus <HealthStatus[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
Get-VirtualDisk [-UniqueId <String[]>] [-Usage <Usage[]>] [-OtherUsageDescription <String[]>]
 [-IsSnapshot <Boolean[]>] [-HealthStatus <HealthStatus[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByName
```
Get-VirtualDisk [-Name <String[]>] [-Usage <Usage[]>] [-OtherUsageDescription <String[]>]
 [-IsSnapshot <Boolean[]>] [-HealthStatus <HealthStatus[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageJob
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-StorageJob <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByTargetVirtualDisk
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-TargetVirtualDisk <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### BySourceVirtualDisk
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-SourceVirtualDisk <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByTargetPort
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-TargetPort <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByInitiatorId
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-InitiatorId <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByMaskingSet
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-MaskingSet <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByInitiatorPort
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-InitiatorPort <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByDisk
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-Disk <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByStorageTier
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-StorageTier <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByPhysicalDisk
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-PhysicalDisk <CimInstance>] [-PhysicalRangeMin <UInt64>]
 [-PhysicalRangeMax <UInt64>] [-NoRedundancy] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStoragePool
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-StoragePool <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageNode
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-StorageNode <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageSubSystem
```
Get-VirtualDisk [-Usage <Usage[]>] [-OtherUsageDescription <String[]>] [-IsSnapshot <Boolean[]>]
 [-HealthStatus <HealthStatus[]>] [-StorageSubSystem <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VirtualDisk** cmdlet returns a list of VirtualDisk objects, across all storage pools, across all providers, or optionally a filtered subset based on provided criteria.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-VirtualDisk
```

This example returns all VirtualDisk objects across all visible StoragePool objects, across all visible StorageProvider objects.

### EXAMPLE 2
```
PS C:\> $stpool = (Get-StoragePool -FriendlyName "SpacesPool")
PS C:\> Get-VirtualDisk -StoragePool $stpool
```

This example lists only the virtual disks from the StoragePool object named SpacesPool.

### EXAMPLE 3
```
PS C:\> Get-VirtualDisk | Where-Object -FilterScript {$_.HealthStatus -Ne "Healthy"}
```

This example lists all virtual disks, across all pools, and all providers, which are not currently in a healthy state.

### EXAMPLE 4
```
PS C:\> Get-VirtualDisk -FriendlyName "VDisk01" | Get-Disk | Get-Partition | Get-Volume
```

This example gets the partition and volume associated with a virtual disk.
The command gets the virtual disk named VDisk01 and passes the virtual disk to the Get-Disk cmdlet by using the pipeline operator.
The Get-Disk cmdlet gets the disk associated with the virtual disk and passes the disk to the Get-Partition by using the pipeline operator.
The Get-Partition cmdlet gets the partition associated with the disk, and passes the partition to the Get-Volume cmdlet by using the pipeline operator.
The Get-Volume cmdlet gets the volume associated with the partition.

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

### -Disk
Accepts a Disk object as input.
The Disk CIM object is exposed by the [Get-Disk](https://technet.microsoft.com/library/3929eb27-1365-42ca-8acf-68b364c3599f) cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -FriendlyName
Specifies a friendly name for a disk.
The friendly name may be defined by a user and is not guaranteed to be unique.

```yaml
Type: String[]
Parameter Sets: ByFriendlyName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HealthStatus
Specifies the status of an object and indicates if the object is **Healthy** or **Warning Unhealthy**.

```yaml
Type: HealthStatus[]
Parameter Sets: (All)
Aliases:
Accepted values: Healthy, Warning, Unhealthy, Unknown

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitiatorId
Accepts an InitiatorId object as input.
The Initiator ID CIM object is exposed by the [Get-InitiatorId](https://technet.microsoft.com/library/56c96b69-33c0-402b-8813-d64a4434011d) cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByInitiatorId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InitiatorPort
Accepts an InitiatorPort object as input.
The Initiator Port CIM object is exposed by the [Get-InitiatorPort](https://technet.microsoft.com/library/580a19cf-26d1-45bb-ad34-a6265e2efacf) cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByInitiatorPort
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IsSnapshot
Specifies that the virtual disk is a snapshot of another virtual disk.

```yaml
Type: Boolean[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaskingSet
Accepts a MaskingSet object as input.
The Masking Set CIM object is exposed by the [Get-MaskingSet](https://technet.microsoft.com/library/a7ef71fd-f7f6-4231-8799-0e96dd9eac84) cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByMaskingSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of an object or setting.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoRedundancy
Indicates that this cmdlet gets virtual disks that have one remaining copy of data stored on the physical disk.

```yaml
Type: SwitchParameter
Parameter Sets: ByPhysicalDisk
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
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalDisk
Accepts a PhysicalDisk object as input.
The Physical Disk CIM object is exposed by the [Get-PhysicalDisk](https://technet.microsoft.com/library/a204dcde-bfac-43ac-9b79-d81384f255be) cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByPhysicalDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PhysicalRangeMax
This parameter is reserved for future use.

```yaml
Type: UInt64
Parameter Sets: ByPhysicalDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalRangeMin
This parameter is reserved for future use.

```yaml
Type: UInt64
Parameter Sets: ByPhysicalDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceVirtualDisk
Specifies a virtual disk as a **CIMInstance** object.
The cmdlet gets the snapshot or clone virtual disks that were created from the virtual disk that you specify.
To obtain a virtual disk object, use the Get-VirtualDisk cmdlet.

```yaml
Type: CimInstance
Parameter Sets: BySourceVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageJob
Specifies an outstanding storage job as a **CIMInstance** object.
The cmdlet gets the virtual disks associated with the storage jobs that you specify.
To obtain a virtual disk object, use the Get-StorageJob cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStorageJob
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageNode
Specifies a storage node as a **CIMInstance** object.
The cmdlet gets the virtual disks that belong to the storage node that you specify.
The virtual disks that belong to the storage node have read/write permissions on the node.
To obtain a virtual disk object, use the Get-StorageNode cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStorageNode
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StoragePool
Accepts a StoragePool object as input.
The Storage Pool CIM object is exposed by the [Get-StoragePool](https://technet.microsoft.com/library/288acad9-7678-45c2-b7b4-3a0522fea499) cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStoragePool
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageSubSystem
Accepts a StorageSubsystem object as input.
The Storage Subsystem CIM object is exposed by the [Get-StorageSubsystem](https://technet.microsoft.com/library/ea364a0b-06d6-4653-b41c-be69b8038b54) cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStorageSubSystem
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageTier
Specifies a storage tier as a **CIMInstance** object.
The cmdlet gets the virtual disks included in the storage tier that you specify.
To obtain a virtual disk object, use the Get-StorageTier cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStorageTier
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetPort
Accepts a TargetPort object as input.
The Target Port CIM object is exposed by the [Get-TargetPort](https://technet.microsoft.com/library/4c139739-cda3-4379-b87b-60b1b4db8cd2) cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByTargetPort
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetVirtualDisk
Specifies a virtual disk as a **CIMInstance** object.
The cmdlet gets the virtual disk from which the snapshot or clone virtual disk that you specify were created.
To obtain a virtual disk object, use the Get-VirtualDisk cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByTargetVirtualDisk
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
Specifies an ID used to uniquely identify a Disk object in the system.
The ID persists through restarts.

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Usage
Indicates the intended usage of the virtual disk.

```yaml
Type: Usage[]
Parameter Sets: (All)
Aliases:
Accepted values: Unknown, Other, Unrestricted, ReservedForComputerSystem, ReservedForReplicationServices, ReservedForMigrationServices, LocalReplicaSource, RemoteReplicaSource, LocalReplicaTarget, RemoteReplicaTarget, LocalReplicaSourceOrTarget, RemoteReplicaSourceOrTarget, DeltaReplicaTarget, ElementComponent, ReservedAsPoolContributer, CompositeVolumeMember, CompositeVirtualDiskMember, ReservedForSparing

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Disk
You can use the pipeline operator to pass an MSFT_Disk object to the **Disk** parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_InitiatorId
You can use the pipeline operator to pass an MSFT_InitiatorId object to the **InitiatorId** parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_InitiatorPort
You can use the pipeline operator to pass an MSFT_InitiatorPort object to the **InitiatorPort** parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_MaskingSet
You can use the pipeline operator to pass an MSFT_MaskingSet object to the **MaskingSet** parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
You can use the pipeline operator to pass an MSFT_PhysicalDisk object to the **PhysicalDisk** parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubsystem
You can use the pipeline operator to pass an MSFT_StorageSubsystem object to the **StorageSubsystem** parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageTier
You can use the pipeline operator to pass an MSFT_StorageTier object to the **StorageTier** parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_TargetPort
You can use the pipeline operator to pass an MSFT_TargetPort object to the **TargetPort** parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_TargetVirtualDisk
You can use the pipeline operator to pass an MSFT_TargetVirtualDisk object to the **TargetVirtualDisk** parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
This cmdlet outputs an object that represents the specified virtual disk. For more information about output object type, see [MSFT_VirtualDisk class](/windows-hardware/drivers/storage/msft-virtualdisk).

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Where-Object](https://go.microsoft.com/fwlink/?LinkID=113423)

[Connect-VirtualDisk](./Connect-VirtualDisk.md)

[Disconnect-VirtualDisk](./Disconnect-VirtualDisk.md)

[Get-Partition](./Get-Partition.md)

[Get-StoragePool](./Get-StoragePool.md)

[Hide-VirtualDisk](./Hide-VirtualDisk.md)

[New-VirtualDisk](./New-VirtualDisk.md)

[Remove-VirtualDisk](./Remove-VirtualDisk.md)

[Repair-VirtualDisk](./Repair-VirtualDisk.md)

[Resize-VirtualDisk](./Resize-VirtualDisk.md)

[Set-VirtualDisk](./Set-VirtualDisk.md)

[Show-VirtualDisk](./Show-VirtualDisk.md)
