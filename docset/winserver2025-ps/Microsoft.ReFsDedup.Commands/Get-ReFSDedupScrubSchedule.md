---
external help file: Microsoft.ReFsDedup.Commands.dll-Help.xml
Module Name: Microsoft.ReFsDedup.Commands
ms.date: 11/20/2024
online version: https://learn.microsoft.com/powershell/module/microsoft.refsdedup.commands/get-refsdedupscrubschedule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ReFSDedupScrubSchedule
---

# Get-ReFSDedupScrubSchedule

## SYNOPSIS
Retrieves the deduplication scrub schedule on the specified ReFS volume.

## SYNTAX

```
Get-ReFSDedupScrubSchedule [-Volume] <String> [<CommonParameters>]
```

## DESCRIPTION

The `Get-ReFSDedupScrubSchedule` cmdlet retrieves the deduplication scrub schedule on the specified
ReFS volume.

## EXAMPLES

### Example 1

```powershell
Get-ReFSDedupScrubSchedule -Volume "D:"
```

This example gets the deduplication scrub schedule on the `D:` ReFS volume.

## PARAMETERS

### -Volume

Specifies the volume on which to retrieve the ReFS deduplication scrub schedule. Enter one or more
volume IDs, drive letters, or volume GUID paths. For drive letters, use the format `D:`. For volume
GUID paths, use the format `\\?\Volume{{GUID}}\`. Separate multiple volumes with a comma.

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

[Clear-ReFSDedupScrubSchedule](Clear-ReFSDedupScrubSchedule.md)

[Set-ReFSDedupScrubSchedule](Set-ReFSDedupScrubSchedule.md)
