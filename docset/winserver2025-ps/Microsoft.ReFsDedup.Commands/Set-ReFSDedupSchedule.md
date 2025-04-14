---
external help file: Microsoft.ReFsDedup.Commands.dll-Help.xml
Module Name: Microsoft.ReFsDedup.Commands
ms.date: 11/20/2024
online version: https://learn.microsoft.com/powershell/module/microsoft.refsdedup.commands/set-refsdedupschedule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ReFSDedupSchedule
---

# Set-ReFSDedupSchedule

## SYNOPSIS
Sets the deduplication schedule on a specified ReFS volume.

## SYNTAX

```
Set-ReFSDedupSchedule [-Volume] <String> -Start <DateTime> [-Duration <TimeSpan>] -Days <DaysOfWeek>
 [-CpuPercentage <UInt32>] [-ConcurrentOpenFiles <UInt32>] [-MinimumLastModifiedTimeHours <Int32>]
 [-ExcludeFileExtension <String[]>] [-ExcludeFolder <String[]>] [-CompressionFormat <Format>]
 [-CompressionLevel <UInt16>] [-CompressionChunkSize <UInt32>] [-CompressionTuning <UInt32>]
 [-RecompressionTuning <UInt32>] [-DecompressionTuning <UInt32>] [<CommonParameters>]
```

## DESCRIPTION

The `Set-ReFSDedupSchedule` cmdlet sets the deduplication schedule for a specified ReFS volume. You
can use this cmdlet to specify when and how often deduplication should run on the volume.

## EXAMPLES

### Example 1

```powershell
Set-ReFSDedupSchedule -Volume "D:" -Start "10:00 PM" -Days Monday,Wednesday,Friday -Duration 4:00:00
```

This example sets the deduplication schedule for the `D:` ReFS volume to run on `Monday`, `Wednesday`,
and `Friday` at `10:00 PM` for `4` hours.

## PARAMETERS

### -CompressionChunkSize

Specifies the chunk size to use during compression.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CompressionFormat

Specifies the compression format to use during deduplication. Acceptable values are:

- `LZ4`
- `Uncompressed`
- `Unknown`
- `ZSTD`

```yaml
Type: Format
Parameter Sets: (All)
Aliases:
Accepted values: Unknown, Uncompressed, LZ4, ZSTD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CompressionLevel

Specifies the compression level to use during deduplication.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CompressionTuning

Specifies the compression tuning to use during deduplication.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConcurrentOpenFiles

Specifies the maximum number of files that can be open at the same time during deduplication.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CpuPercentage

Specifies the maximum percentage of CPU usage that deduplication should consume.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Days

Specifies the days of the week on which deduplication should run on the volume. Acceptable values
are:

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

### -DecompressionTuning

Specifies the decompression tuning to use during deduplication.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Duration

Specifies the duration for which deduplication should run on the volume.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludeFileExtension

Specifies one or more file extensions to exclude from deduplication.

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

### -ExcludeFolder

Specifies one or more folders to exclude from deduplication.

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

### -MinimumLastModifiedTimeHours

Specifies the minimum number of hours that must elapse before a file can be deduplicated.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecompressionTuning

Specifies the recompression tuning to use during deduplication.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Start

Specifies the date and time when deduplication should start running on the volume.

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

Specifies the ReFS volume for which to set the deduplication schedule. Enter one or more volume
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

[Suspend-ReFSDedupSchedule](Suspend-ReFSDedupSchedule.md)
