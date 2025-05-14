---
description: The Get-PmemPhysicalDevice cmdlet gets the physical devices associated with persistent memory.
external help file: Microsoft.Storage.PersistentMemory.Management.Commands.dll-Help.xml
Module Name: PersistentMemory
ms.date: 09/24/2021
online version: https://learn.microsoft.com/powershell/module/persistentmemory/get-pmemphysicaldevice?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PmemPhysicalDevice
---

# Get-PmemPhysicalDevice

## SYNOPSIS
Gets the physical devices associated with persistent memory.

## SYNTAX

### AllDevices (Default)
```
Get-PmemPhysicalDevice [<CommonParameters>]
```

### ByDeviceId
```
Get-PmemPhysicalDevice [[-DeviceId] <String[]>] [<CommonParameters>]
```

### ByPmemDisk
```
Get-PmemPhysicalDevice [-LogicalDisk <PmemDisk>] [<CommonParameters>]
```

### ByDiskNumber
```
Get-PmemPhysicalDevice [-DiskNumber <UInt32>] [<CommonParameters>]
```

### ByInputObject
```
Get-PmemPhysicalDevice [-InputObject <CimInstance>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-PmemPhysicalDevice** cmdlet gets the physical devices associated with persistent memory.

## EXAMPLES

### Example 1: Get physical devices that have persistent memory
```powershell
Get-PmemPhysicalDevice
```

```output
DeviceId DeviceType           HealthStatus OperationalStatus PhysicalLocation FirmwareRevision Persistent memory size Volatile
                                                                                                                      memory size
-------- ----------           ------------ ----------------- ---------------- ---------------- ---------------------- --------------
1020     Intel INVDIMM device Healthy      {Ok}              CPU2_DIMM_C1     102005310        126 GB                 0 GB
1120     Intel INVDIMM device Healthy      {Ok}              CPU2_DIMM_F1     102005310        126 GB                 0 GB
120      Intel INVDIMM device Healthy      {Ok}              CPU1_DIMM_F1     102005310        126 GB                 0 GB
20       Intel INVDIMM device Healthy      {Ok}              CPU1_DIMM_C1     102005310        126 GB                 0 GB
```

This command gets all the physical devices with persistent memory.


### Example 2: Get physical device for a persistent memory disk
```powershell
(Get-PmemDisk)[0] | Get-PmemPhysicalDevice
```

```output
DeviceId DeviceType           HealthStatus OperationalStatus PhysicalLocation FirmwareRevision Persistent memory size Volatile memory size
-------- ----------           ------------ ----------------- ---------------- ---------------- ---------------------- --------------------
20       Intel INVDIMM device Healthy      {Ok}              CPU1_DIMM_C1     102005310        126 GB                 0 GB
120      Intel INVDIMM device Healthy      {Ok}              CPU1_DIMM_F1     102005310        126 GB                 0 GB
```

This example uses the **Get-PmemDisk** cmdlet to get a persistent memory disk and gets the physical device for that disk.

## PARAMETERS

### -DeviceId
Specifies the device ID of the physical device to get.

```yaml
Type: String[]
Parameter Sets: ByDeviceId
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskNumber
Specifies the disk number of persistent memory disk.
The cmdlet gets the physical device for that disk.

```yaml
Type: UInt32
Parameter Sets: ByDiskNumber
Aliases:

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

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LogicalDisk
Specifies a logical persistent memory disk.
The cmdlet gets the physical device for that disk.

```yaml
Type: PmemDisk
Parameter Sets: ByPmemDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Storage.PersistentMemory.Management.PmemDisk

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### Microsoft.Storage.PersistentMemory.Management.PmemPhysicalDevice

## NOTES

## RELATED LINKS

[Get-PmemDisk](Get-PmemDisk.md)

[Initialize-PmemPhysicalDevice](Initialize-PmemPhysicalDevice.md)
