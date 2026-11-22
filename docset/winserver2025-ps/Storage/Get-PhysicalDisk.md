---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-physicaldisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PhysicalDisk
---

# Get-PhysicalDisk

## SYNOPSIS
Gets a list of all PhysicalDisk objects visible across any available Storage Management Providers, or optionally a filtered list.

## SYNTAX

### ByUniqueId (Default)
```
Get-PhysicalDisk [-UniqueId <String>] [-Usage <PhysicalDiskUsage>] [-Description <String>]
 [-Manufacturer <String>] [-Model <String>] [-CanPool <Boolean>] [-HealthStatus <PhysicalDiskHealthStatus>]
 [-CimSession <CimSession>] [<CommonParameters>]
```

### ByObjectId
```
Get-PhysicalDisk [-ObjectId <String>] [-Usage <PhysicalDiskUsage>] [-Description <String>]
 [-Manufacturer <String>] [-Model <String>] [-CanPool <Boolean>] [-HealthStatus <PhysicalDiskHealthStatus>]
 [-CimSession <CimSession>] [<CommonParameters>]
```

### ByName
```
Get-PhysicalDisk [[-FriendlyName] <String>] [[-SerialNumber] <String>] [-Usage <PhysicalDiskUsage>]
 [-Description <String>] [-Manufacturer <String>] [-Model <String>] [-CanPool <Boolean>]
 [-HealthStatus <PhysicalDiskHealthStatus>] [-CimSession <CimSession>] [<CommonParameters>]
```

### ByInputObject
```
Get-PhysicalDisk -InputObject <CimInstance> [-CimSession <CimSession>] [<CommonParameters>]
```

### ByStorageSubsystem
```
Get-PhysicalDisk -StorageSubsystem <CimInstance> [-Usage <PhysicalDiskUsage>] [-Description <String>]
 [-Manufacturer <String>] [-Model <String>] [-CanPool <Boolean>] [-HealthStatus <PhysicalDiskHealthStatus>]
 [-CimSession <CimSession>] [<CommonParameters>]
```

### ByStorageEnclosure
```
Get-PhysicalDisk -StorageEnclosure <CimInstance> [-Usage <PhysicalDiskUsage>] [-Description <String>]
 [-Manufacturer <String>] [-Model <String>] [-CanPool <Boolean>] [-HealthStatus <PhysicalDiskHealthStatus>]
 [-CimSession <CimSession>] [<CommonParameters>]
```

### ByStorageNode
```
Get-PhysicalDisk -StorageNode <CimInstance> [-PhysicallyConnected] [-Usage <PhysicalDiskUsage>]
 [-Description <String>] [-Manufacturer <String>] [-Model <String>] [-CanPool <Boolean>]
 [-HealthStatus <PhysicalDiskHealthStatus>] [-CimSession <CimSession>] [<CommonParameters>]
```

### ByStoragePool
```
Get-PhysicalDisk -StoragePool <CimInstance> [-Usage <PhysicalDiskUsage>] [-Description <String>]
 [-Manufacturer <String>] [-Model <String>] [-CanPool <Boolean>] [-HealthStatus <PhysicalDiskHealthStatus>]
 [-CimSession <CimSession>] [<CommonParameters>]
```

### ByVirtualDisk
```
Get-PhysicalDisk -VirtualDisk <CimInstance> [-VirtualRangeMin <UInt64>] [-VirtualRangeMax <UInt64>]
 [-HasAllocations <Boolean>] [-SelectedForUse <Boolean>] [-NoRedundancy] [-Usage <PhysicalDiskUsage>]
 [-Description <String>] [-Manufacturer <String>] [-Model <String>] [-CanPool <Boolean>]
 [-HealthStatus <PhysicalDiskHealthStatus>] [-CimSession <CimSession>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-PhysicalDisk** cmdlet gets a list of all PhysicalDisk objects visible across any available Storage Management Providers, or optionally a filtered list of disks.

## EXAMPLES

### Example 1: Getting all physical disks
```
PS C:\> Get-PhysicalDisk
FriendlyName        CanPool            OperationalStatus   HealthStatus        Usage                              Size
------------        --------            -----------------   ------------        -----                              ----
PhysicalDisk4       False               OK                  Healthy             Data Store                        25 GB
```

This example returns an array of all PhysicalDisk objects present in the computer.
A storage management provider is required to manage physical disks.

### Example 2: Getting all physical disks eligible for adding to a storage pool
```
PS C:\>Get-PhysicalDisk -CanPool $True
```

This example returns an array of PhysicalDisk objects that are available for adding to a storage pool (they are in a primordial pool).

## PARAMETERS

### -CanPool
Gets physical disks that are available for use in a storage pool.

```yaml
Type: Boolean
Parameter Sets: ByUniqueId, ByObjectId, ByName, ByStorageSubsystem, ByStorageEnclosure, ByStorageNode, ByStoragePool, ByVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -Description
Gets the physical disks that contain the specified description.
Enter a description or use wildcard characters to enter a description pattern.

```yaml
Type: String
Parameter Sets: ByUniqueId, ByObjectId, ByName, ByStorageSubsystem, ByStorageEnclosure, ByStorageNode, ByStoragePool, ByVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Gets the physical disk with the specified friendly name.
Enter a friendly name or use wildcard characters to enter a name pattern.

```yaml
Type: String
Parameter Sets: ByName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -HasAllocations
Indicates whether the cmdlet gets a list of physical disks that host the extents of the virtual disk that you specify by using the *VirtualDisk* parameter.

```yaml
Type: Boolean
Parameter Sets: ByVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HealthStatus
Specifies the **health status** of physical disks.
The acceptable values for this parameter are:

- Healthy
- Unhealthy
- Unknown
- Warning

```yaml
Type: PhysicalDiskHealthStatus
Parameter Sets: ByUniqueId, ByObjectId, ByName, ByStorageSubsystem, ByStorageEnclosure, ByStorageNode, ByStoragePool, ByVirtualDisk
Aliases:
Accepted values: Healthy, Warning, Unhealthy, Unknown

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Manufacturer
Gets the physical disks with the specified manufacturer.
Enter a manufacturer string or use wildcard characters to enter a pattern.

```yaml
Type: String
Parameter Sets: ByUniqueId, ByObjectId, ByName, ByStorageSubsystem, ByStorageEnclosure, ByStorageNode, ByStoragePool, ByVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Model
Gets the physical disks of the specified model.
Enter a model string or use wildcard characters to enter a pattern.

```yaml
Type: String
Parameter Sets: ByUniqueId, ByObjectId, ByName, ByStorageSubsystem, ByStorageEnclosure, ByStorageNode, ByStoragePool, ByVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoRedundancy
Indicates that this cmdlet gets physical disks that contain the last remaining copy of the data of a virtual disk.

```yaml
Type: SwitchParameter
Parameter Sets: ByVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ObjectId
Specifies the ID of the physical disk to get.

```yaml
Type: String
Parameter Sets: ByObjectId
Aliases: PhysicalDiskObjectId

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PhysicallyConnected
Indicates that this cmdlet gets physical disks that are physically connected to the specified storage node.

```yaml
Type: SwitchParameter
Parameter Sets: ByStorageNode
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SelectedForUse
Indicates whether the cmdlet gets a list of physical disks to host the extents that belong to the virtual disk specified by the *VirtualDisk* parameter.
Specify the physical disks to host the extents of a virtual disk by using the *PhysicalDisksToUse* parameter of the **New-VirtualDisk** cmdlet.

```yaml
Type: Boolean
Parameter Sets: ByVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SerialNumber
Specifies the serial number of the physical disk to get.

```yaml
Type: String
Parameter Sets: ByName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageEnclosure
Specifies a storage enclosure associated with the physical disk that this cmdlet gets.
To obtain a **StorageEnclosure** object, use the **Get-StorageEnclosure** cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStorageEnclosure
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageNode
Specifies a storage node as a **CimInstance** object.
The cmdlet gets the physical disk connected to the node that you specify.
To obtain a storage node object, use the **Get-StorageNode** cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStorageNode
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StoragePool
Accepts a StoragePool object as input and gets the physical disks that belong to the pool.
The Storage Pool CIM object is exposed by the **Get-StoragePool** cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStoragePool
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageSubsystem
Specifies a storage subsystem.
This cmdlet gets physical disks attached to the storage subsystem that you specify.
To obtain a **StorageSubsystem** object, use the **Get-StorageSubSystem** cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStorageSubsystem
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -UniqueId
Gets only the physical disks with the specified IDs.
Type one or more IDs (separated by commas), or use wildcard characters to enter a pattern.

```yaml
Type: String
Parameter Sets: ByUniqueId
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Usage
Specifies an allocation method or usage.
This cmdlet gets the physical disks that have the specified allocation method.
The acceptable values for this parameter are:

- AutoSelect
- HotSpare
- Journal
- ManualSelect
- Retired
- Unknown

```yaml
Type: PhysicalDiskUsage
Parameter Sets: ByUniqueId, ByObjectId, ByName, ByStorageSubsystem, ByStorageEnclosure, ByStorageNode, ByStoragePool, ByVirtualDisk
Aliases:
Accepted values: Unknown, AutoSelect, ManualSelect, HotSpare, Retired, Journal

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDisk
Accepts a VirtualDisk object as input and gets the physical disks used by the virtual disk.
The VirtualDisk object is exposed by the **Get-VirtualDisk** cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByVirtualDisk
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualRangeMax
This parameter is reserved for future use.

```yaml
Type: UInt64
Parameter Sets: ByVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualRangeMin
This parameter is reserved for future use.

```yaml
Type: UInt64
Parameter Sets: ByVirtualDisk
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
You can use the pipeline operator to pass an MSFT_StoragePool object to the *StoragePool* parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubsystem
You can use the pipeline operator to pass an MSFT_StorageSubsystem object to the *StorageSubsystem* parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
You can use the pipeline operator to pass an MSFT_VirtualDisk object to the *VirtualDisk* parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
The Get-PhysicalDisk cmdlet returns objects that represent physical disks.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Add-PhysicalDisk](./Add-PhysicalDisk.md)

[Get-StorageEnclosure](./Get-StorageEnclosure.md)

[Get-StoragePool](./Get-StoragePool.md)

[Get-StorageSubSystem](./Get-StorageSubsystem.md)

[New-StoragePool](./New-StoragePool.md)

[Remove-PhysicalDisk](./Remove-PhysicalDisk.md)

[Reset-PhysicalDisk](./Reset-PhysicalDisk.md)

[Set-PhysicalDisk](./Set-PhysicalDisk.md)

[New-VirtualDisk](./New-VirtualDisk.md)

[Get-StorageNode](./Get-StorageNode.md)
