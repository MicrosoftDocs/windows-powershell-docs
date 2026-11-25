---
external help file: Microsoft.ReFsDedup.Commands.dll-Help.xml
Module Name: Microsoft.ReFsDedup.Commands
ms.date: 11/20/2024
online version: https://learn.microsoft.com/powershell/module/microsoft.refsdedup.commands/get-refsdedupstatus?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ReFSDedupStatus
---

# Get-ReFSDedupStatus

## SYNOPSIS
Retrieves the status of data deduplication on a specified ReFS volume.

## SYNTAX

```
Get-ReFSDedupStatus [-Volume] <String> [<CommonParameters>]
```

## DESCRIPTION

The `Get-ReFSDedupStatus` cmdlet retrieves the status of data deduplication on a specified ReFS
volume.

## EXAMPLES

### Example 1

```powershell
Get-ReFSDedupStatus -Volume "D:"
```

This example retrieves the deduplication status for the `D:` ReFS volume.

### Example 2

```powershell
$Volumes = "E:", "F:"
foreach ($Volume in $Volumes) {
   Get-ReFSDedupStatus -Volume $Volume
}
```

This example retrieves the deduplication status for both the `E:` and `F:` ReFS volume.

## PARAMETERS

### -Volume

Specifies the ReFS volume for which to retrieve the deduplication status. Enter one or more volume
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
