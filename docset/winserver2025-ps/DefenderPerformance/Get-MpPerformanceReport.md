---
external help file: MSFT_MpPerformanceRecording.psm1-help.xml
Module Name: DefenderPerformance
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/defenderperformance/get-mpperformancereport?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-MpPerformanceReport
---

# Get-MpPerformanceReport

## SYNOPSIS
This cmdlet reports the file paths, file extensions, and processes that cause the highest impact to
Microsoft Defender Antivirus scans.

## SYNTAX

```
Get-MpPerformanceReport [-Path] <String> [-TopFiles <Int32>] [-TopScansPerFile <Int32>]
 [-TopProcessesPerFile <Int32>] [-TopScansPerProcessPerFile <Int32>] [-TopPaths <Int32>]
 [-TopPathsDepth <Int32>] [-TopScansPerPath <Int32>] [-TopFilesPerPath <Int32>]
 [-TopScansPerFilePerPath <Int32>] [-TopExtensionsPerPath <Int32>]
 [-TopScansPerExtensionPerPath <Int32>] [-TopProcessesPerPath <Int32>]
 [-TopScansPerProcessPerPath <Int32>] [-TopExtensions <Int32>] [-TopScansPerExtension <Int32>]
 [-TopPathsPerExtension <Int32>] [-TopScansPerPathPerExtension <Int32>]
 [-TopFilesPerExtension <Int32>] [-TopScansPerFilePerExtension <Int32>]
 [-TopProcessesPerExtension <Int32>] [-TopScansPerProcessPerExtension <Int32>]
 [-TopProcesses <Int32>] [-TopScansPerProcess <Int32>] [-TopFilesPerProcess <Int32>]
 [-TopScansPerFilePerProcess <Int32>] [-TopExtensionsPerProcess <Int32>]
 [-TopScansPerExtensionPerProcess <Int32>] [-TopPathsPerProcess <Int32>]
 [-TopScansPerPathPerProcess <Int32>] [-TopScans <Int32>] [-MinDuration <String>]
 [-MinStartTime <DateTime>] [-MinEndTime <DateTime>] [-MaxStartTime <DateTime>]
 [-MaxEndTime <DateTime>] [-Overview] [-Raw] [<CommonParameters>]
```

## DESCRIPTION

This cmdlet analyzes a previously collected Microsoft Defender Antivirus performance recording and
reports the file paths, file extensions and processes that cause the highest impact to Microsoft
Defender Antivirus scans.

The performance analyzer provides insight into problematic files that could cause performance
degradation of Microsoft Defender Antivirus. This tool is provided "AS IS", and is not intended to
provide suggestions on exclusions. Exclusions can reduce the level of protection on your endpoints.
Exclusions, if any, should be defined with caution.

## EXAMPLES

### EXAMPLE 1

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopFiles:10 -TopExtensions:10 -TopProcesses:10 -TopScans:10
```

### EXAMPLE 2

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopFiles:10 -TopExtensions:10 -TopProcesses:10 -TopScans:10 -Raw | ConvertTo-Json
```

### EXAMPLE 3

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:10
```

### EXAMPLE 4

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopFiles:10
```

### EXAMPLE 5

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopFiles:10 -TopScansPerFile:3
```

### EXAMPLE 6

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopFiles:10 -TopProcessesPerFile:3
```

### EXAMPLE 7

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopFiles:10 -TopProcessesPerFile:3 -TopScansPerProcessPerFile:3
```

### EXAMPLE 8

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopPaths:10
```

### EXAMPLE 9

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopPaths:10 -TopPathsDepth:3
```

### EXAMPLE 10

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopPaths:10 -TopPathsDepth:3 -TopScansPerPath:3
```

### EXAMPLE 11

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopPaths:10 -TopScansPerPath:3
```

### EXAMPLE 12

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopPaths:10 -TopPathsDepth:3 -TopFilesPerPath:3
```

### EXAMPLE 13

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopPaths:10 -TopFilesPerPath:3
```

### EXAMPLE 14

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopPaths:10 -TopPathsDepth:3 -TopFilesPerPath:3 -TopScansPerFilePerPath:3
```

### EXAMPLE 15

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopPaths:10 -TopFilesPerPath:3 -TopScansPerFilePerPath:3
```

### EXAMPLE 16

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopPaths:10 -TopPathsDepth:3 -TopExtensionsPerPath:3
```

### EXAMPLE 17

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopPaths:10 -TopExtensionsPerPath:3
```

### EXAMPLE 18

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopPaths:10 -TopPathsDepth:3 -TopExtensionsPerPath:3 -TopScansPerExtensionPerPath:3
```

### EXAMPLE 19

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopPaths:10 -TopExtensionsPerPath:3 -TopScansPerExtensionPerPath:3
```

### EXAMPLE 20

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopPaths:10 -TopPathsDepth:3 -TopProcessesPerPath:3
```

### EXAMPLE 21

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopPaths:10 -TopProcessesPerPath:3
```

### EXAMPLE 22

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopPaths:10 -TopPathsDepth:3 -TopProcessesPerPath:3 -TopScansPerProcessPerPath:3
```

### EXAMPLE 23

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopPaths:10 -TopProcessesPerPath:3 -TopScansPerProcessPerPath:3
```

### EXAMPLE 24

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopExtensions:10
```

### EXAMPLE 25

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopExtensions:10 -TopScansPerExtension:3
```

### EXAMPLE 26

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopExtensions:10 -TopPathsPerExtension:3
```

### EXAMPLE 27

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopExtensions:10 -TopPathsPerExtension:3 -TopPathsDepth:3
```

### EXAMPLE 28

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopExtensions:10 -TopPathsPerExtension:3 -TopPathsDepth:3 -TopScansPerPathPerExtension:3
```

### EXAMPLE 29

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopExtensions:10 -TopPathsPerExtension:3 -TopScansPerPathPerExtension:3
```

### EXAMPLE 30

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopExtensions:10 -TopFilesPerExtension:3
```

### EXAMPLE 31

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopExtensions:10 -TopFilesPerExtension:3 -TopScansPerFilePerExtension:3
```

### EXAMPLE 32

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopExtensions:10 -TopProcessesPerExtension:3
```

### EXAMPLE 33

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopExtensions:10 -TopProcessesPerExtension:3 -TopScansPerProcessPerExtension:3
```

### EXAMPLE 34

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopProcesses:10
```

### EXAMPLE 35

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopProcesses:10 -TopScansPerProcess:3
```

### EXAMPLE 36

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopProcesses:10 -TopExtensionsPerProcess:3
```

### EXAMPLE 37

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopProcesses:10 -TopExtensionsPerProcess:3 -TopScansPerExtensionPerProcess:3
```

### EXAMPLE 38

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopProcesses:10 -TopFilesPerProcess:3
```

### EXAMPLE 39

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopProcesses:10 -TopFilesPerProcess:3 -TopScansPerFilePerProcess:3
```

### EXAMPLE 40

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopProcesses:10 -TopPathsPerProcess:3
```

### EXAMPLE 41

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopProcesses:10 -TopPathsPerProcess:3 -TopPathsDepth:3
```

### EXAMPLE 42

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopProcesses:10 -TopPathsPerProcess:3 -TopPathsDepth:3 -TopScansPerPathPerProcess:3
```

### EXAMPLE 43

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopProcesses:10 -TopPathsPerProcess:3 -TopScansPerPathPerProcess:3
```

### EXAMPLE 44

Find top 10 scans with longest durations that both start and end between MinStartTime and
MaxEndTime:

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:10 -MinStartTime:"5/14/2022 7:01:11 AM" -MaxEndTime:"5/14/2022 7:01:41 AM"
```

### EXAMPLE 45

Find top 10 scans with longest durations between MinEndTime and MaxStartTime, possibly partially
overlapping this period

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:10 -MinEndTime:"5/14/2022 7:01:11 AM" -MaxStartTime:"5/14/2022 7:01:41 AM"
```

### EXAMPLE 46

Find top 10 scans with longest durations between MinStartTime and MaxStartTime, possibly partially
overlapping this period

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:10 -MinStartTime:"5/14/2022 7:01:11 AM" -MaxStartTime:"5/14/2022 7:01:41 AM"
```

### EXAMPLE 47

Find top 10 scans with longest durations that start at MinStartTime or later:

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:10 -MinStartTime:"5/14/2022 7:01:11 AM"
```

### EXAMPLE 48

Find top 10 scans with longest durations that start before or at MaxStartTime:

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:10 -MaxStartTime:"5/14/2022 7:01:11 AM"
```

### EXAMPLE 49

Find top 10 scans with longest durations that end at MinEndTime or later:

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:10 -MinEndTime:"5/14/2022 7:01:11 AM"
```

### EXAMPLE 50

Find top 10 scans with longest durations that end before or at MaxEndTime:

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:10 -MaxEndTime:"5/14/2022 7:01:11 AM"
```

### EXAMPLE 51

Find top 10 scans with longest durations, impacting the current interval, that did not start or end between MaxStartTime and MinEndTime.

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:10 -MaxStartTime:"5/14/2022 7:01:11 AM" -MinEndTime:"5/14/2022 7:01:41 AM"
```

### EXAMPLE 52

Find top 10 scans with longest durations, impacting the current interval, that started between MinStartTime and MaxStartTime, and ended later than MinEndTime.

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:10 -MinStartTime:"5/14/2022 7:00:00 AM" -MaxStartTime:"5/14/2022 7:01:11 AM" -MinEndTime:"5/14/2022 7:01:41 AM"
```

### EXAMPLE 53

Find top 10 scans with longest durations, impacting the current interval, that started before MaxStartTime, and ended between MinEndTime and MaxEndTime.

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:10 -MaxStartTime:"5/14/2022 7:01:11 AM" -MinEndTime:"5/14/2022 7:01:41 AM" -MaxEndTime:"5/14/2022 7:02:00 AM"
```

### EXAMPLE 54

Find top 10 scans with longest durations, impacting the current interval, that started between MinStartTime and MaxStartTime, and ended between MinEndTime and MaxEndTime.

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:10 -MinStartTime:"5/14/2022 7:00:00 AM" -MaxStartTime:"5/14/2022 7:01:11 AM" -MinEndTime:"5/14/2022 7:01:41 AM" -MaxEndTime:"5/14/2022 7:02:00 AM"
```

### EXAMPLE 55

Find top 10 scans with longest durations that both start and end between MinStartTime and
MaxEndTime, using DateTime as raw numbers in FILETIME format, e.g. from -Raw report format:

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:10 -MinStartTime:([DateTime]::FromFileTime(132969744714304340)) -MaxEndTime:([DateTime]::FromFileTime(132969745000971033))
```

### EXAMPLE 56

Find top 10 scans with longest durations between MinEndTime and MaxStartTime, possibly partially
overlapping this period, using DateTime as raw numbers in FILETIME format, e.g. from -Raw report
format:

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:10 -MinEndTime:([DateTime]::FromFileTime(132969744714304340)) -MaxStartTime:([DateTime]::FromFileTime(132969745000971033))
```

### EXAMPLE 57

Display a summary or overview of the scans captured in the trace, in addition to the information
displayed regularly through other arguments. Output is influenced by time interval arguments
MinStartTime and MaxEndTime.

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl [other arguments] -Overview
```

## PARAMETERS

### -MaxEndTime

Specifies the maximum end time of scans included in the report.
Accepts a valid DateTime.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: [DateTime]::MaxValue
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxStartTime

Specifies the maximum start time of scans included in the report. Accepts a valid DateTime.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: [DateTime]::MaxValue
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinDuration

Specifies the minimum duration of any scans or total scan durations of files, extensions and
processes included in the report. Accepts values like '0.1234567sec' or '0.1234ms' or '0.1us' or a
valid TimeSpan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0us
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinEndTime

Specifies the minimum end time of scans included in the report. Accepts a valid DateTime.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: [DateTime]::MinValue
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinStartTime

Specifies the minimum start time of scans included in the report. Accepts a valid DateTime.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: [DateTime]::MinValue
Accept pipeline input: False
Accept wildcard characters: False
```

### -Overview

Adds an overview or summary of the scans captured in the trace to the regular output.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Specifies the location of Microsoft Defender Antivirus performance recording to analyze.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Raw

Specifies that the output should be machine readable and readily convertible to serialization
formats like JSON.

- Collections and elements are not be formatted.
- TimeSpan values are represented as number of 100-nanosecond intervals.
- DateTime values are represented as number of 100-nanosecond intervals since January 1, 1601 (UTC).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopExtensions

Requests a top extensions report and specifies how many top extensions to output, sorted by
"Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopExtensionsPerPath

Specifies how many top extensions to output for each top path, sorted by "Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopExtensionsPerProcess

Specifies how many top extensions to output for each top process, sorted by "Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopFiles

Requests a top files report and specifies how many top files to output, sorted by "Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopFilesPerExtension

Specifies how many top files to output for each top extension, sorted by "Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopFilesPerPath

Specifies how many top files to output for each top path, sorted by "Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopFilesPerProcess

Specifies how many top files to output for each top process, sorted by "Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopPaths

Requests a top paths report and specifies how many top entries to output, sorted by "Duration". This
is called recursively for each directory entry. Scans are grouped hierarchically per folder and
sorted by "Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopPathsDepth

Specifies the maxmimum depth (path-wise) that will be used to group scans when $TopPaths is used.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopPathsPerExtension

Specifies how many top paths to output for each top extension, sorted by "Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopPathsPerProcess

Specifies how many top paths to output for each top process, sorted by "Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopProcesses

Requests a top processes report and specifies how many top processes to output, sorted by
"Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopProcessesPerExtension

Specifies how many top processes to output for each top extension, sorted by "Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopProcessesPerFile

Specifies how many top processes to output for each top file, sorted by "Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopProcessesPerPath

Specifies how many top processes to output for each top path, sorted by "Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopScans

Requests a top scans report and specifies how many top scans to output, sorted by "Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopScansPerExtension

Specifies how many top scans to output for each top extension, sorted by "Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopScansPerExtensionPerPath

Specifies how many top scans to output for each top extension for each top path, sorted by
"Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopScansPerExtensionPerProcess

Specifies how many top scans to output for each top extension for each top process, sorted by
"Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopScansPerFile

Specifies how many top scans to output for each top file, sorted by "Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopScansPerFilePerExtension

Specifies how many top scans to output for each top file for each top extension, sorted by
"Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopScansPerFilePerPath

Specifies how many top scans to output for each top file for each top path, sorted by "Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopScansPerFilePerProcess

Specifies how many top scans to output for each top file for each top process, sorted by "Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopScansPerPath

Specifies how many top scans to output for each top path, sorted by "Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopScansPerPathPerExtension

Specifies how many top scans to output for each top path for each top extension, sorted by
"Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopScansPerPathPerProcess

Specifies how many top scans to output for each top path for each top process, sorted by "Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopScansPerProcess

Specifies how many top scans to output for each top process in the Top Processes report, sorted by
"Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopScansPerProcessPerExtension

Specifies how many top scans to output for each top process for each top extension, sorted by
"Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopScansPerProcessPerFile

Specifies how many top scans to output for each top process for each top file, sorted by "Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopScansPerProcessPerPath

Specifies how many top scans to output for each top process for each top path, sorted by "Duration".

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
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
