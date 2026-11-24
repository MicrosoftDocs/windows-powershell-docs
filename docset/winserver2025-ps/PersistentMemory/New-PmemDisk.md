---
description: The New-PmemDisk cmdlet creates a persistent memory disk in an unused persistent memory region or a simulated persistent memory disk.
external help file: Microsoft.Storage.PersistentMemory.Management.Commands.dll-Help.xml
Module Name: PersistentMemory
ms.date: 09/24/2021
online version: https://learn.microsoft.com/powershell/module/persistentmemory/new-pmemdisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-PmemDisk
---

# New-PmemDisk

## SYNOPSIS
Creates a persistent memory disk in an unused persistent memory region.

## SYNTAX

### NormalDisk
```
New-PmemDisk -RegionId <UInt32[]> [-FriendlyName <String[]>] [-DiskSizeInBytes <UInt64[]>]
 [-AtomicityType <NAMESPACE_ATOMICITY_TYPE[]>] [<CommonParameters>]
```

### SimulatedDisk
```
New-PmemDisk -DiskSizeInBytes <UInt64[]> [-AtomicityType <NAMESPACE_ATOMICITY_TYPE[]>] [-Simulated]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-PmemDisk** cmdlet creates a persistent memory disk in an unused persistent memory region.
A persistent memory is a contiguously addressed range of non-volatile memory.
You can think of it as a hard disk partition or LUN.

The cmdlet can also create a simulated persistent memory disk that isn't in persistent memory.

## EXAMPLES

### Example 1: Create a disk
```powershell
New-PmemDisk -RegionId 1 -AtomicityType BlockTranslationTable
```

This example creates a disk in the specified persistent memory region.
The disk uses a block transfer table.

### Example 2: Create a simulated persistent memory disk
```powershell
New-PmemDisk -DiskSizeInBytes 270582939648 -Simulated
```

This example creates a simulated persistent memory disk of the specified size.

### Example 3: Create multiple disks
```powershell
Get-PmemUnusedRegion | New-PmemDisk
```

This example gets an unused persistent memory region.
The command creates multiple persistent memory disks in the unused regions.

## PARAMETERS

### -AtomicityType
Specifies whether to use a block translation table.
A block translation table enables block-like sector writes.
Applications can avoid mixing old and new data in a failure scenario.

Valid values are `None` and `BlockTranslationTable`. The default value is `None`.

You can't change the atomicity type after you create a disk.

We strongly recommend `BlockTranslationTable` in nearly all cases.

```yaml
Type: NAMESPACE_ATOMICITY_TYPE[]
Parameter Sets: (All)
Aliases:
Accepted values: None, BlockTranslationTable

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskSizeInBytes
Specifies the size of the persistent memory disk.

```yaml
Type: UInt64[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Specifies a friendly name for the persistent memory disk.

```yaml
Type: String[]
Parameter Sets: NormalDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RegionId
Specifies the ID of the region for the persistent memory disk.

```yaml
Type: UInt32[]
Parameter Sets: NormalDisk
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Simulated
Indicates that the command creates a simulated persistent memory disk.
You can create a simulated disk without persistent memory hardware.

```yaml
Type: SwitchParameter
Parameter Sets: SimulatedDisk
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.UInt32[]

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-PmemDisk](Get-PmemDisk.md)

[Get-PmemUnusedRegion](Get-PmemUnusedRegion.md)

[Remove-PmemDisk](Remove-PmemDisk.md)
