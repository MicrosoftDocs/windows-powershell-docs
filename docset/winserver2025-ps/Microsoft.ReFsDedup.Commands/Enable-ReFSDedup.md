---
external help file: Microsoft.ReFsDedup.Commands.dll-Help.xml
Module Name: Microsoft.ReFsDedup.Commands
ms.date: 11/20/2024
online version: https://learn.microsoft.com/powershell/module/microsoft.refsdedup.commands/enable-refsdedup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ReFSDedup
---

# Enable-ReFSDedup

## SYNOPSIS
Enables data deduplication on a specified ReFS volume.

## SYNTAX

```
Enable-ReFSDedup [-Volume] <String> [-Type] <DedupVolumeType> [<CommonParameters>]
```

## DESCRIPTION

The `Enable-ReFSDedup` cmdlet enables data deduplication on a specified ReFS volume. You can
specify the type of deduplication to use with the `-Type` parameter.

## EXAMPLES

### Example 1

```powershell
Enable-ReFSDedup -Volume "D:" -Type DedupAndCompress
```

This example enables data deduplication with compression on the `D:` ReFS volume.

### Example 2

```powershell
Enable-ReFSDedup -Volume "E:, F:" -Type DedupAndCompress
```

This example enables data deduplication with compression on both `E:` and `F:` ReFS volumes.

## PARAMETERS

### -Type

Specifies the type of deduplication to use. Acceptable values are:

- `Compress`
- `Dedup`
- `DedupAndCompress`

```yaml
Type: DedupVolumeType
Parameter Sets: (All)
Aliases:
Accepted values: Dedup, DedupAndCompress, Compress

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Volume

Specifies the volume or volumes to enable ReFS data deduplication. Enter one or more volume IDs,
drive letters, or volume GUID paths. For drive letters, use the format `D:`. For volume GUID paths,
use the format `\\?\Volume{{GUID}}\`. Separate multiple volumes with a comma.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Disable-ReFSDedup](Disable-ReFSDedup.md)
