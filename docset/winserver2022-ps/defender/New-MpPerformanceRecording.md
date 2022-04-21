---
description: Use this topic to render performance recording of Microsoft Defender Antivirus scans.
external help file: MSFT_MpThreat.cdxml-help.xml
Module Name: Defender
ms.date: 03/20/2022
online version: 
schema: 2.0.0
title: New-MpPerformanceRecording
---

# New-MpPerformanceRecording

## SYNOPSIS

Collects a performance recording of Microsoft Defender Antivirus scans.


## SYNTAX

### DefaultSet (Default)

```
New-MpPerformanceRecording -RecordTo <String>
```

### ById

```
New-MpPerformanceRecording [-RecordTo ]  
```

## DESCRIPTION

The `New-MpPerformanceRecording` cmdlet collects a performance recording of Microsoft Defender Antivirus scans. These performance recordings contain Microsoft-Antimalware-Engine and NT kernel process events and can be analyzed after collection using the [Get-MpPerformanceReport](#get-mpperformancereport) cmdlet.

This `New-MpPerformanceRecording` cmdlet provides an insight into problematic files that could cause a degradation in the performance of Microsoft Defender Antivirus. This tool is provided “AS IS”, and is not intended to provide suggestions on exclusions. Exclusions can reduce the level of protection on your endpoints. Exclusions, if any, should be defined with caution.

For more information on the performance analyzer, see [Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer) docs.

> [!IMPORTANT]
> This cmdlet requires elevated administrator privileges.

**Supported OS versions**

Windows Version 10 and later.

> [!NOTE]
> This feature is available starting with platform version 4.18.2108.X and later.

## EXAMPLES

### Example 1: Collect a performance recording and save it

```powershell
New-MpPerformanceRecording -RecordTo:.\Defender-scans.etl
```

The above command collects a performance recording and saves it to the specified path: **.\Defender-scans.etl**.

### Example 2: Collect a performance recording for Remote PowerShell session

```powershell
$s = New-PSSession -ComputerName Server02 -Credential Domain01\User01
New-MpPerformanceRecording -RecordTo C:\LocalPathOnServer02\trace.etl -Session $s
```

The above command collects a performance recording on Server02 (as specified by argument $s of parameter Session) and saves it to the specified path: **C:\LocalPathOnServer02\trace.etl** on Server02.

## PARAMETERS

### -RecordTo

Specifies the location in which to save the Microsoft Defender Antimalware performance recording.

```yaml
Type: String
Position: Named
Default value: None
Accept pipeline input: False 
Accept wildcard characters: False
```

### -Session

Specifies the PSSession object in which to create and save the Microsoft Defender Antivirus performance recording. When you use this parameter the RecordTo parameter refers to the local path on the remote machine. Available with Defender platform version 4.18.2201.10.

```yaml
Type: PSSession[]
Position: 0
Default value: None
Accept pipeline input: False 
Accept wildcard characters: False

### CommonParameters

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-MpPerformanceReport](Get-MpPerformanceReport.md)

