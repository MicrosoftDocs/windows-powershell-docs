---
external help file: Microsoft.ReFsDedup.Commands.dll-Help.xml
Module Name: Microsoft.ReFsDedup.Commands
ms.date: 11/20/2024
online version: https://learn.microsoft.com/powershell/module/microsoft.refsdedup.commands/stop-refsdedupjob?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-ReFSDedupJob
---

# Stop-ReFSDedupJob

## SYNOPSIS
Stops a running deduplication job on a specified ReFS volume.

## SYNTAX

```
Stop-ReFSDedupJob [-Volume] <String> [<CommonParameters>]
```

## DESCRIPTION

The `Stop-ReFSDedupJob` cmdlet stops a running deduplication job on a specified ReFS volume that is
currently running.

## EXAMPLES

### Example 1

```powershell
Stop-ReFSDedupJob -Volume "D:"
```

This example stops the deduplication job for the `D:` ReFS volume.

## PARAMETERS

### -Volume

Specifies the ReFS volume for which to stop the deduplication job. Enter one or more volume IDs,
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

[Start-ReFSDedupJob](Start-ReFSDedupJob.md)
