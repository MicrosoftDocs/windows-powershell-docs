---
external help file: Microsoft.ReFsDedup.Commands.dll-Help.xml
Module Name: Microsoft.ReFsDedup.Commands
ms.date: 11/20/2024
online version: https://learn.microsoft.com/powershell/module/microsoft.refsdedup.commands/start-refsdedupjob?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-ReFSDedupJob
---

# Start-ReFSDedupJob

## SYNOPSIS
Starts a deduplication job on the specified ReFS volume.

## SYNTAX

```
Start-ReFSDedupJob [-Volume] <String> [-Duration <TimeSpan>] [-FullRun] [-CpuPercentage <UInt32>]
 [-ConcurrentOpenFiles <UInt32>] [-MinimumLastModifiedTimeHours <Int32>]
 [-ExcludeFileExtension <String[]>] [-ExcludeFolder <String[]>] [-CompressionFormat <Format>]
 [-CompressionLevel <UInt16>] [-CompressionChunkSize <UInt32>] [-CompressionTuning <UInt32>]
 [-RecompressionTuning <UInt32>] [-DecompressionTuning <UInt32>] [<CommonParameters>]
```

## DESCRIPTION

The `Start-ReFSDedupJob` cmdlet starts a deduplication job on the specified ReFS volume or to
resume an existing job that was previously paused or stopped.

## EXAMPLES

### Example 1

```powershell
Start-ReFSDedupJob -Volume "D:"
```

This example starts a deduplication job on the `D:` drive using the default settings.

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

Specifies the compression format to use during the job. Acceptable values are:

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

Specifies the compression level to use during the job.

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

Specifies the compression tuning to use during the job.

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

Specifies the maximum number of files that can be open concurrently during the job.

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

Specifies the maximum percentage of CPU to use during the job.

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

### -DecompressionTuning

Specifies the decompression tuning to use during the job.

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

Specifies the duration of the job.

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

Specifies one or more file extensions to exclude from the job.

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

Specifies one or more folders to exclude from the job.

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

### -FullRun

Indicates whether to run a full deduplication job on the specified ReFS volume. If this parameter
isn't specified, the job will run in incremental mode where only new or changed files will be
processed.

```yaml
Type: SwitchParameter
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

### -Volume

Specifies the ReFS volume on which to run the job. Enter one or more volume IDs, drive letters, or
volume GUID paths. For drive letters, use the format `D:`. For volume GUID paths, use the format
`\\?\Volume{{GUID}}\`. Separate multiple volumes with a comma.

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

[Stop-ReFSDedupJob](Stop-ReFSDedupJob.md)
