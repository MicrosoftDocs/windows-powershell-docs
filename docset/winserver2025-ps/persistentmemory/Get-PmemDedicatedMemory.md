---
description: The Get-PmemDedicatedMemory cmdlet gets dedicated persistent memory.
external help file: Microsoft.Storage.PersistentMemory.Management.Commands.dll-Help.xml
Module Name: PersistentMemory
ms.date: 09/24/2021
online version: https://learn.microsoft.com/powershell/module/persistentmemory/get-pmemdedicatedmemory?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PmemDedicatedMemory
---

# Get-PmemDedicatedMemory

## SYNOPSIS
Gets dedicated persistent memory.

## SYNTAX

### AllDevices (Default)
```
Get-PmemDedicatedMemory [<CommonParameters>]
```

### SingleDevice
```
Get-PmemDedicatedMemory [[-DeviceNumber] <UInt32[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-PmemDedicatedMemory** cmdlet gets dedicated persistent memory. You can display all dedicated persistent memory or memory for a specific device.

## EXAMPLES

### Example 1: Get all dedicated persistent memory
```powershell
Get-PmemDedicatedMemory
```

This example gets all dedicated memory.

### Example 2: Get dedicated persistent memory on a device
```powershell
Get-PmemDedicatedMemory -DeviceNumber 1
```

This example gets all dedicated memory for the specified device.

## PARAMETERS

### -DeviceNumber
Specifies the device number for the physical device.
The cmdlet gets dedicated memory for that device.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[New-PmemDedicatedMemory](New-PmemDedicatedMemory.md)

[Remove-PmemDedicatedMemory](Remove-PmemDedicatedMemory.md)
