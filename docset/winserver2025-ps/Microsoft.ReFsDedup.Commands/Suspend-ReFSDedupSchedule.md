---
external help file: Microsoft.ReFsDedup.Commands.dll-Help.xml
Module Name: Microsoft.ReFsDedup.Commands
ms.date: 11/20/2024
online version: https://learn.microsoft.com/powershell/module/microsoft.refsdedup.commands/suspend-refsdedupschedule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-ReFSDedupSchedule
---

# Suspend-ReFSDedupSchedule

## SYNOPSIS
Suspends the deduplication schedule on a specified ReFS volume.

## SYNTAX

```
Suspend-ReFSDedupSchedule [-Volume] <String> [<CommonParameters>]
```

## DESCRIPTION

The `Suspend-ReFSDedupSchedule` cmdlet suspends the deduplication schedule on the specified ReFS
volume. When you suspend the schedule, no new deduplication jobs will be started until you resume
the schedule.

## EXAMPLES

### Example 1

```powershell
Suspend-ReFSDedupSchedule -Volume "D:"
```

This example suspends the deduplication schedule on the `D:` ReFS volume.

## PARAMETERS

### -Volume

Specifies the volume on which to suspend the ReFS Deduplication schedule. Enter one or more volume
IDs, drive letters, or volume GUID paths. For drive letters, use the format `D:`. For volume GUID
paths, use the format `\\?\Volume{{GUID}}\`. Separate multiple volumes with a comma.

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

[Clear-ReFSDedupSchedule](Clear-ReFSDedupSchedule.md)

[Get-ReFSDedupSchedule](Get-ReFSDedupSchedule.md)

[Resume-ReFSDedupSchedule](Resume-ReFSDedupSchedule.md)

[Set-ReFSDedupSchedule](Set-ReFSDedupSchedule.md)
