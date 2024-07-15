---
external help file: Microsoft.ReFsDedup.Commands.dll-Help.xml
Module Name: Microsoft.ReFsDedup.Commands
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/microsoft.refsdedup.commands/set-refsdedupschedule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ReFSDedupSchedule
---

# Set-ReFSDedupSchedule

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

```
Set-ReFSDedupSchedule [-Volume] <String> -Start <DateTime> [-Duration <TimeSpan>] -Days <DaysOfWeek>
 [-CpuPercentage <UInt32>] [-ConcurrentOpenFiles <UInt32>] [-MinimumLastModifiedTimeHours <Int32>]
 [-ExcludeFileExtension <String[]>] [-ExcludeFolder <String[]>] [-CompressionFormat <Format>]
 [-CompressionLevel <UInt16>] [-CompressionChunkSize <UInt32>] [-CompressionTuning <UInt32>]
 [-RecompressionTuning <UInt32>] [-DecompressionTuning <UInt32>] [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -CompressionChunkSize
{{ Fill CompressionChunkSize Description }}

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CompressionFormat
{{ Fill CompressionFormat Description }}

```yaml
Type: Microsoft.ReFS.DeDup.Format
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
{{ Fill CompressionLevel Description }}

```yaml
Type: System.UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CompressionTuning
{{ Fill CompressionTuning Description }}

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConcurrentOpenFiles
{{ Fill ConcurrentOpenFiles Description }}

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CpuPercentage
{{ Fill CpuPercentage Description }}

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Days
{{ Fill Days Description }}

```yaml
Type: Microsoft.ReFS.DeDup.DaysOfWeek
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
{{ Fill DecompressionTuning Description }}

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Duration
{{ Fill Duration Description }}

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludeFileExtension
{{ Fill ExcludeFileExtension Description }}

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludeFolder
{{ Fill ExcludeFolder Description }}

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumLastModifiedTimeHours
{{ Fill MinimumLastModifiedTimeHours Description }}

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecompressionTuning
{{ Fill RecompressionTuning Description }}

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Start
{{ Fill Start Description }}

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Volume
{{ Fill Volume Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
