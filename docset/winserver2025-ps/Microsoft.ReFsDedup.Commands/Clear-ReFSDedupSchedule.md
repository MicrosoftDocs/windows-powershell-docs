---
external help file: Microsoft.ReFsDedup.Commands.dll-Help.xml
Module Name: Microsoft.ReFsDedup.Commands
ms.date: 11/20/2024
online version: https://learn.microsoft.com/powershell/module/microsoft.refsdedup.commands/clear-refsdedupschedule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-ReFSDedupSchedule
---

# Clear-ReFSDedupSchedule

## SYNOPSIS
Clears the scheduled task for deduplication on a specified ReFS volume.

## SYNTAX

```
Clear-ReFSDedupSchedule [-Volume] <String> [<CommonParameters>]
```

## DESCRIPTION

The `Clear-ReFSDedupSchedule` cmdlet clears the scheduled job, including the schedule itself, for
deduplication on the specified ReFS volume.

## EXAMPLES

### Example 1

```powershell
Clear-ReFSDedupSchedule -Volume "D:"
```

This example clears the scheduled task for volume `D:`.

## PARAMETERS

### -Volume

Specifies the volume or volumes to clear the scheduled optimization task. Enter one or more volume
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

[Get-ReFSDedupSchedule](Get-ReFSDedupSchedule.md)

[Resume-ReFSDedupSchedule](Resume-ReFSDedupSchedule.md)

[Set-ReFSDedupSchedule](Set-ReFSDedupSchedule.md)

[Suspend-ReFSDedupSchedule](Suspend-ReFSDedupSchedule.md)
