---
external help file: Microsoft.ReFsDedup.Commands.dll-Help.xml
Module Name: Microsoft.ReFsDedup.Commands
ms.date: 11/20/2024
online version: https://learn.microsoft.com/powershell/module/microsoft.refsdedup.commands/set-refsdedupscrubschedule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ReFSDedupScrubSchedule
---

# Set-ReFSDedupScrubSchedule

## SYNOPSIS
Sets the deduplication scrub schedule on the specified ReFS volume.

## SYNTAX

```
Set-ReFSDedupScrubSchedule [-Volume] <String> -Start <DateTime> -Days <DaysOfWeek>
 -WeeksInterval <UInt16> [-DedupDataOnly <Boolean>] [<CommonParameters>]
```

## DESCRIPTION

The `Set-ReFSDedupScrubSchedule` cmdlet sets the deduplication scrub schedule on the specified ReFS
volume. The scrub schedule specifies when and how often scrub jobs are run on the volume.

## EXAMPLES

### Example 1

```powershell
$params = @{
    Volume        = "D:"
    Start         = "12/01/2024 8:00 AM"
    Days          = "Monday,Thursday"
    WeeksInterval = 2
}
Set-ReFSDedupScrubSchedule @params
```

This example sets the deduplication scrub schedule on the `D:` ReFS volume to run every `Monday` and
`Thursday` at `8:00 AM`, starting on December 1st, 2024, and running every `2` weeks.

## PARAMETERS

### -Days

Specifies the days of the week on which to run the scrub schedule. Acceptable values are:

- `None`
- `EveryDay`
- `Monday`
- `Tuesday`
- `Wednesday`
- `Thursday`
- `Friday`
- `Saturday`
- `Sunday`

```yaml
Type: DaysOfWeek
Parameter Sets: (All)
Aliases:
Accepted values: None, Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, EveryDay

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DedupDataOnly

Specifies whether to include only deduplicated data in the scrub schedule.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Start

Specifies the date and time on which to start the scrub schedule.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Volume

Specifies the ReFS volume on which to set the deduplication scrub schedule. Enter one or more volume
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

### -WeeksInterval

Specifies the number of weeks between each run of the scrub schedule.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
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

[Get-ReFSDedupScrubSchedule](Get-ReFSDedupScrubSchedule.md)
