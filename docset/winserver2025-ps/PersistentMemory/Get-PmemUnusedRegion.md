---
description: The Get-PmemUnusedRegion cmdlet gets unused regions in persistent memory.
external help file: Microsoft.Storage.PersistentMemory.Management.Commands.dll-Help.xml
Module Name: PersistentMemory
ms.date: 09/24/2021
online version: https://learn.microsoft.com/powershell/module/persistentmemory/get-pmemUnusedregion?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PmemUnusedRegion
---

# Get-PmemUnusedRegion

## SYNOPSIS
Gets unused regions in persistent memory.

## SYNTAX

```
Get-PmemUnusedRegion [[-RegionId] <UInt32[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-PmemUnusedRegion** cmdlet gets unused regions of persistent memory.
Use this cmdlet with the **New-PmemDisk** cmdlet to create persistent memory disks.

## EXAMPLES

### Example 1: Get unused regions
```powershell
Get-PmemUnusedRegion
```

```output
RegionId TotalSizeInBytes DeviceId
-------- ---------------- --------
       1     270582939648 {20, 120}
       3     270582939648 {1020, 1120}
```

This example gets all the unused regions of persistent memory.

### Example 1: Get a specific region
```powershell
Get-PmemUnusedRegion -RegionId 3
```

```output
RegionId TotalSizeInBytes DeviceId
-------- ---------------- --------
       3     270582939648 {1020, 1120}
```

This example gets all the unused regions of persistent memory.

## PARAMETERS

### -RegionId
Specifies the ID of the region of the persistent memory disk to get.

```yaml
Type: UInt32[]
Parameter Sets: (All)
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

[Get-PmemDisk](Get-PmemDisk.md)

[New-PmemDisk](New-PmemDisk.md)
