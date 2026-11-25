---
external help file: MSFT_MpPerformanceRecording.psm1-help.xml
Module Name: DefenderPerformance
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/defenderperformance/new-mpperformancerecording?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-MpPerformanceRecording
---

# New-MpPerformanceRecording

## SYNOPSIS
This cmdlet collects a performance recording of Microsoft Defender Antivirus
scans.

## SYNTAX

### Interactive (Default)

```
New-MpPerformanceRecording -RecordTo <String> [-Session <PSSession[]>] [-WPRPath <String>]
 [<CommonParameters>]
```

### Timed

```
New-MpPerformanceRecording -RecordTo <String> -Seconds <Int32> [-Session <PSSession[]>]
[-WPRPath <String>] [<CommonParameters>]
```

## DESCRIPTION

This cmdlet collects a performance recording of Microsoft Defender Antivirus scans. These
performance recordings contain Microsoft-Antimalware-Engine and NT kernel process events and can be
analyzed after collection using the Get-MpPerformanceReport cmdlet.

This cmdlet requires elevated administrator privileges.

The performance analyzer provides insight into problematic files that could cause performance
degradation of Microsoft Defender Antivirus. This tool is provided "AS IS", and is not intended to
provide suggestions on exclusions. Exclusions can reduce the level of protection on your endpoints.
Exclusions, if any, should be defined with caution.

## EXAMPLES

### EXAMPLE 1

```
New-MpPerformanceRecording -RecordTo:.\Defender-scans.etl
```

## PARAMETERS

### -RecordTo

Specifies the location where to save the Microsoft Defender Antivirus performance recording.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Seconds

Specifies the duration of the performance recording in seconds.

```yaml
Type: System.Int32
Parameter Sets: Timed
Aliases:

Required: True
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -Session

Specifies the PSSession object in which to create and save the Microsoft Defender Antivirus
performance recording. When you use this parameter, the RecordTo parameter refers to the local path
on the remote machine.

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WPRPath

Optional argument to specifiy a different tool for recording traces. Default is wpr.exe When
$Session parameter is used this path represents a location on the remote machine.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
