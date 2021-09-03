---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_MpPerformanceReport.cdxml-help.xml
Module Name: Defender
ms.date: 08/25/2021
online version: https://docs.microsoft.com/powershell/module/defender/get-mpperformancereport?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-MpPerformanceReport
---

# Get-MpPerformanceReport

## SYNOPSIS
Analyzes and reports on Microsoft Defender Antivirus (MDAV) performance recording.

## SYNTAX

```
Get-MpPerformanceReport    [-Path] <String>
[-TopScans <Int32>]
[-TopFiles  <Int32>
[ -TopScansPerFile <Int32>]
[-TopProcessesPerFile  <Int32>  
	[-TopScansPerProcessPerFile <Int32>]
	]
] 
[-TopExtensions  <Int32>
[-TopScansPerExtension <Int32>
[-TopProcessesPerExtension <Int32>
	[-TopScansPerProcessPerExtension <Int32>]
	]

[-TopFilesPerExtension  <Int32>
	[-TopScansPerFilePerExtension <Int32>]
	]
] 
[-TopProcesses  <Int32>
	[-TopScansPerProcess <Int32>]
	[-TopExtensionsPerProcess <Int32>
		[-TopScansPerExtensionPerProcess <Int32>]
		]
[-TopFilesPerProcess  <Int32>
	[-TopScansPerFilePerProcess <Int32>]
]
```

## DESCRIPTION

The `Get-MpPerformanceReport` cmdlet analyzes a previously collected Microsoft Defender Antivirus performance recording ([New-MpPerformanceRecording](New-MpPerformanceRecording.md#new-mpperformancerecording)) and reports the file paths, file extensions, and processes that cause the highest impact to Microsoft Defender Antivirus scans.

The performance analyzer provides an insight into problematic files that could cause a degradation in the performance of Microsoft Defender Antivirus. This tool is provided "AS IS" and is not intended to provide suggestions on exclusions. Exclusions can reduce the level of protection on your endpoints. Exclusions, if any, should be defined with caution.

For more information on the performance analyzer, see Performance Analyzer docs.

**Supported OS versions**

Windows Version 10 and later.

> [!NOTE]
> This feature is available starting with platform version 4.18.2108.X and later.

## PARAMETERS

### -MinDuration
Specifies the minimum duration of any scan or total scan durations of files, extensions, and processes included in the report; accepts values like  **0.1234567sec**, **0.1234ms**, **0.1us**, or a valid TimeSpan.

```yaml
Type: String
Position: Named
Default value: None
Accept pipeline input: False 
Accept wildcard characters: False
```

### -Path
Specifies the path(s) to one or more locations.

```yaml
Type: String
Position: 0
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -TopScans
Requests a top-scans report and specifies how many top scans to output, sorted by "Duration".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopFiles
Requests a top-files report and specifies how many top files to output, sorted by "Duration".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### --TopScansPerFile
Specifies how many top scans to output for each top file, sorted by "Duration”.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopProcessesPerFile
Specifies how many top processes to output for each top file, sorted by "Duration “.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopScansPerProcessPerFile
Specifies how many top scans for output for each top process for each top file, sorted by "Duration”.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopExtensions 
Specifies how many top extensions to output, sorted by "Duration”.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopScansPerExtension
Specifies how many top scans to output for each top extension, sorted by "Duration".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopProcessesPerExtension 
Specifies how many top processes to output for each top extension, sorted by "Duration”.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopScansPerProcessPerExtension
Specifies how many top scans for output for each top process for each top extension, sorted by "Duration”.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopFilesPerExtension 
Specifies how many top files to output for each top extension, sorted by "Duration".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopScansPerFilePerExtension 
Specifies how many top scans to output for each top file for each top extension, sorted by "Duration".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopProcesses
Requests a top-processes report and specifies how many of the top processes to output, sorted by "Duration”.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopScansPerProcess 
Specifies how many top scans to output for each top process in the Top Processes report, sorted by "Duration”.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopExtensionsPerProcess 
Specifies how many top extensions to output for each top process, sorted by "Duration”.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopScansPerExtensionPerProcess 
Specifies how many top scans to output for each top extension for each top process, sorted by "Duration”.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopFilesPerProcess
Specifies how many top files to output for each top process, sorted by "Duration".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopScansPerFilePerProcess 
Specifies how many top scans for output for each top file for each top process, sorted by "Duration”.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## RELATED LINKS

- [New-MpPerformanceRecording](New-MpPerformanceRecording.md#new-mpperformancerecording)
- Performance Analyzer docs
