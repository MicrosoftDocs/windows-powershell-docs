---
external help file: Microsoft.ReFsDedup.Commands.dll-Help.xml
Module Name: Microsoft.ReFsDedup.Commands
ms.date: 11/20/2024
online version: https://learn.microsoft.com/powershell/module/microsoft.refsdedup.commands/resume-refsdedupschedule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-ReFSDedupSchedule
---

# Resume-ReFSDedupSchedule

## SYNOPSIS
Resumes the deduplication schedule on a specified ReFS volume.

## SYNTAX

```
Resume-ReFSDedupSchedule [-Volume] <String> [<CommonParameters>]
```

## DESCRIPTION

The `Resume-ReFSDedupSchedule` cmdlet resumes the deduplication schedule on a specified ReFS
volume that has been paused or stopped.

## EXAMPLES

### Example 1

```powershell
Resume-ReFSDedupSchedule -Volume "D:"
```

This example resumes the deduplication schedule for the `D:` ReFS volume.

## PARAMETERS

### -Volume

Specifies the ReFS volume for which to resume the deduplication schedule. Enter one or more volume
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

[Set-ReFSDedupSchedule](Set-ReFSDedupSchedule.md)

[Suspend-ReFSDedupSchedule](Suspend-ReFSDedupSchedule.md)
