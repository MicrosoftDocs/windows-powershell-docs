---
external help file: PhysicalDisk.cdxml-help.xml
Module Name: Storage
online version: 
schema: 2.0.0
title: Get-PhysicalDisk
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: A204DCDE-BFAC-43AC-9B79-D81384F255BE
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-PhysicalDisk

## SYNOPSIS
Gets a list of all PhysicalDisk objects visible across any available Storage Management Providers, or optionally a filtered list.

## SYNTAX

### ByUniqueId (Default)
```
Get-PhysicalDisk [-UniqueId <String[]>] [-Usage <Usage[]>] [-Description <String[]>] [-Manufacturer <String[]>]
 [-Model <String[]>] [-CanPool <Boolean[]>] [-HealthStatus <HealthStatus[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectId
```
Get-PhysicalDisk [-ObjectId <String[]>] [-Usage <Usage[]>] [-Description <String[]>] [-Manufacturer <String[]>]
 [-Model <String[]>] [-CanPool <Boolean[]>] [-HealthStatus <HealthStatus[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByName
```
Get-PhysicalDisk [[-FriendlyName] <String[]>] [-Usage <Usage[]>] [-Description <String[]>]
 [-Manufacturer <String[]>] [-Model <String[]>] [-CanPool <Boolean[]>] [-HealthStatus <HealthStatus[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByVirtualDisk
```
Get-PhysicalDisk [-Usage <Usage[]>] [-Description <String[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-CanPool <Boolean[]>] [-HealthStatus <HealthStatus[]>] [-VirtualDisk <CimInstance>]
 [-VirtualRangeMin <UInt64>] [-VirtualRangeMax <UInt64>] [-HasAllocations <Boolean>]
 [-SelectedForUse <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStoragePool
```
Get-PhysicalDisk [-Usage <Usage[]>] [-Description <String[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-CanPool <Boolean[]>] [-HealthStatus <HealthStatus[]>] [-StoragePool <CimInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageNode
```
Get-PhysicalDisk [-Usage <Usage[]>] [-Description <String[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-CanPool <Boolean[]>] [-HealthStatus <HealthStatus[]>] [-StorageNode <CimInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageEnclosure
```
Get-PhysicalDisk [-Usage <Usage[]>] [-Description <String[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-CanPool <Boolean[]>] [-HealthStatus <HealthStatus[]>] [-StorageEnclosure <CimInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageSubSystem
```
Get-PhysicalDisk [-Usage <Usage[]>] [-Description <String[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-CanPool <Boolean[]>] [-HealthStatus <HealthStatus[]>] [-StorageSubSystem <CimInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
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

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete. 

The cmdlet immediately returns an object that represents the job and then displays the command prompt. 
You can continue to work in the session while the job completes. 
To manage the job, use the `*-Job` cmdlets. 
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet. 

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -CanPool
Gets physical disks that are available for use in a storage pool.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -Description
Gets the physical disks that contain the specified description.
Enter a description or use wildcard characters to enter a description pattern.

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

### -FriendlyName
Gets the physical disk with the specified friendly name.
Enter a friendly name or use wildcard characters to enter a name pattern.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Manufacturer
Gets the physical disks with the specified manufacturer.
Enter a manufacturer string or use wildcard characters to enter a pattern.

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

### -Model
Gets the physical disks of the specified model.
Enter a model string or use wildcard characters to enter a pattern.

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

### -ObjectId
Specifies the ID of the physical disk to get.

```yaml
Type: String[]
Parameter Sets: ByObjectId
Aliases: PhysicalDiskObjectId

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -StorageEnclosure
Specifies a storage enclosure associated with the physical disk that this cmdlet gets.
To obtain a **StorageEnclosure** object, use the **Get-StorageEnclosure** cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStorageEnclosure
Aliases: 

Required: False
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

Required: False
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

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageSubSystem
Specifies a storage subsystem.
This cmdlet gets physical disks attached to the storage subsystem that you specify.
To obtain a **StorageSubsystem** object, use the **Get-StorageSubSystem** cmdlet.

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
Gets only the physical disks with the specified IDs.
Type one or more IDs (separated by commas), or use wildcard characters to enter a pattern.

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
Type: Usage[]
Parameter Sets: (All)
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

Required: False
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
You can use the pipeline operator to pass an MSFT_StoragePool object to the StoragePool parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubsystem
You can use the pipeline operator to pass an MSFT_StorageSubsystem object to the StorageSubsystem parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
You can use the pipeline operator to pass an MSFT_VirtualDisk object to the VirtualDisk parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
The Get-PhysicalDisk cmdlet returns objects that represent physical disks.

## NOTES

## RELATED LINKS

[Add-PhysicalDisk](./Add-PhysicalDisk.md)

[Get-StoragePool](./Get-StoragePool.md)

[New-StoragePool](./New-StoragePool.md)

[Remove-PhysicalDisk](./Remove-PhysicalDisk.md)

[Reset-PhysicalDisk](./Reset-PhysicalDisk.md)

[Set-PhysicalDisk](./Set-PhysicalDisk.md)

[New-VirtualDisk](./New-VirtualDisk.md)

[Get-StorageNode](./Get-StorageNode.md)

