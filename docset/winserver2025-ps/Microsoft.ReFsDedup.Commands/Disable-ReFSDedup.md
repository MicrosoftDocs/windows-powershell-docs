---
external help file: Microsoft.ReFsDedup.Commands.dll-Help.xml
Module Name: Microsoft.ReFsDedup.Commands
ms.date: 11/20/2024
online version: https://learn.microsoft.com/powershell/module/microsoft.refsdedup.commands/disable-refsdedup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ReFSDedup
---

# Disable-ReFSDedup

## SYNOPSIS
Disables data deduplication on a specified ReFS volume.

## SYNTAX

```
Disable-ReFSDedup [-Volume] <String> [<CommonParameters>]
```

## DESCRIPTION

The `Disable-ReFSDedup` cmdlet disables data deduplication on a specified ReFS volume. This cmdlet
does not affect existing deduplicated files or folders on the volume, but it prevents new files or
folders from being deduplicated.

## EXAMPLES

### Example 1

```powershell
Disable-ReFSDedup -Volume "D:"
```

This example disables data deduplication on the `D:` ReFS volume.

## PARAMETERS

### -Volume

Specifies the volume or volumes to disable ReFS data deduplication. Enter one or more volume IDs,
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

[Enable-ReFSDedup](Enable-ReFSDedup.md)
