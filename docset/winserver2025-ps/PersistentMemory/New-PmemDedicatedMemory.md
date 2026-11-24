---
description: The New-PmemDedicatedMemory cmdlet creates dedicated persistent memory in the specified region.
external help file: Microsoft.Storage.PersistentMemory.Management.Commands.dll-Help.xml
Module Name: PersistentMemory
ms.date: 09/24/2021
online version: https://learn.microsoft.com/powershell/module/persistentmemory/new-pmemdedicatedmemory?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-PmemDedicatedMemory
---

# New-PmemDedicatedMemory

## SYNOPSIS
Creates dedicated persistent memory in the specified region.

## SYNTAX

```
New-PmemDedicatedMemory -RegionId <UInt32[]> [-FriendlyName <String[]>] [-SizeInBytes <UInt64[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-PmemDedicatedMemory** cmdlet creates dedicated persistent memory in the specified region. You can see unused regions by using the **Get-PmemUnusedRegion** cmdlet.

Small amounts of dedicated storage can be used for memory-mapping data.

## EXAMPLES

### Example 1: Create dedicated persistent memory
```powershell
New-PmemDedicatedMemory -RegionId 1 -SizeInBytes 270582939648
```

This command creates dedicated persistent memory from the region with the ID `1`.

## PARAMETERS

### -FriendlyName
Specifies a friendly name for the dedicated persistent memory.

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

### -RegionId
Specifies the ID of the region for the dedicated persistent memory.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SizeInBytes
Specifies the size of the dedicated persistent memory.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.UInt32[]

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

[Get-PmemUnusedRegion](Get-PmemUnusedRegion.md)

[Get-PmemDedicatedMemory](Get-PmemDedicatedMemory.md)

[Remove-PmemDedicatedMemory](Remove-PmemDedicatedMemory.md)
