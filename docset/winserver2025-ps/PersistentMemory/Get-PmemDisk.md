---
description: The Get-PmemDisk cmdlet gets persistent memory disks.
external help file: Microsoft.Storage.PersistentMemory.Management.Commands.dll-Help.xml
Module Name: PersistentMemory
ms.date: 09/24/2021
online version: https://learn.microsoft.com/powershell/module/persistentmemory/get-pmemdisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PmemDisk
---

# Get-PmemDisk

## SYNOPSIS
Gets persistent memory disks.

## SYNTAX

### AllDisks (Default)
```
Get-PmemDisk [<CommonParameters>]
```

### SingleDevice
```
Get-PmemDisk [[-DiskNumber] <UInt32[]>] [<CommonParameters>]
```

### ByPhysicalDevice
```
Get-PmemDisk [-PhysicalDevice <PmemPhysicalDevice>] [<CommonParameters>]
```

### ByDeviceId
```
Get-PmemDisk [-PhysicalDeviceId <String[]>] [<CommonParameters>]
```

### ByInputObject
```
Get-PmemDisk [-InputObject <CimInstance>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-PmemDisk** cmdlet gets persistent memory disks.
You can get disks by number or physical device.

## EXAMPLES

### Example 1: Get persistent memory disks
```powershell
Get-PmemDisk
```

```output
DiskNumber Size   HealthStatus AtomicityType CanBeRemoved PhysicalDeviceIds UnsafeShutdownCount
---------- ----   ------------ ------------- ------------ ----------------- -------------------
2          252 GB Healthy      None          True         {20, 120}         0
3          252 GB Healthy      None          True         {1020, 1120}      0
```

This example gets all persistent memory disks.

### Example 2: Get persistent memory disk by number
```powershell
Get-PmemDisk -DiskNumber 2
```

```output
DiskNumber Size   HealthStatus AtomicityType CanBeRemoved PhysicalDeviceIds UnsafeShutdownCount
---------- ----   ------------ ------------- ------------ ----------------- -------------------
2          252 GB Healthy      None          True         {20, 120}         0
```

This example gets the specified persistent memory disk.

### Example 3: Get physical disk information
```powershell
Get-PmemDisk | Get-PhysicalDisk | select SerialNumber, HealthStatus, OperationalStatus, OperationalDetails
```

```output
SerialNumber               HealthStatus OperationalStatus  OperationalDetails
------------               ------------ ------------------ ------------------
802c-01-1602-117cb5fc      Healthy      OK
802c-01-1602-117cb64f      Warning      Predictive Failure {Threshold Exceeded,NVDIMM_N Error}
```

This example gets persistent memory disks. It then gets the physical disks that host them and uses the **select** command to display serial number, health status, and operational information.

## PARAMETERS

### -DiskNumber
Specifies the disk number of persistent memory disk to get.

```yaml
Type: UInt32[]
Parameter Sets: SingleDevice
Aliases:

Required: False
Position: 0
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

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PhysicalDevice
Specifies a physical disk.
The cmdlet gets persistent memory disks on the physical disk.

```yaml
Type: PmemPhysicalDevice
Parameter Sets: ByPhysicalDevice
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PhysicalDeviceId
Specifies the ID of a physical disk.
The cmdlet gets persistent memory disks on the physical disk.

```yaml
Type: String[]
Parameter Sets: ByDeviceId
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

### Microsoft.Storage.PersistentMemory.Management.PmemPhysicalDevice

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-PhysicalDisk](../storage/Get-PhysicalDisk.md)

[New-PmemDisk](New-PmemDisk.md)

[Remove-PmemDisk](Remove-PmemDisk.md)
