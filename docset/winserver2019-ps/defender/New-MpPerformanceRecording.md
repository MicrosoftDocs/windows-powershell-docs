---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_MpPerformanceRecording.cdxml-help.xml
Module Name: Defender
ms.date: 08/26/2021
online version: https://docs.microsoft.com/powershell/module/defender/new-mpperformancerecording?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-MpPerformanceRecording
---

# New-MpPerformanceRecording

## SYNOPSIS
Collects a performance recording of MDAV scans.

## SYNTAX

```
New-MpPerformanceRecording
   [-RecordTo <String >]
```

## DESCRIPTION

The `New-MpPerformanceRecording` cmdlet collects a performance recording of Microsoft Defender Antivirus scans. These performance recordings contain Microsoft-Antimalware-Engine and NT kernel process events and can be analyzed after collection using the [Get-MpPerformanceReport](Get-MpPerformanceReport.md#get-mpperformancereport) cmdlet.

This `New-MpPerformanceRecording` cmdlet provides an insight into problematic files that could cause a degradation in the performance of Microsoft Defender Antivirus. This tool is provided “AS IS”, and is not intended to provide suggestions on exclusions. Exclusions can reduce the level of protection on your endpoints. Exclusions, if any, should be defined with caution.

For more information on the Performance analyzer, see Performance Analyzer docs.

> [!IMPORTANT]
> This cmdlet requires elevated administrator privileges.

**Supported OS versions**

Windows Version 10 and higher.

> [!NOTE]
> This feature is available starting with platform version 4.18.2108.X and higher.

## EXAMPLES

```
New-MpPerformanceRecording -RecordTo:.\Defender-scans.etl
```
The above command collects a performance recording and saves it to the specified path: **.\Defender-scans.etl**.

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

## RELATED LINKS

- [Get-MpPerformanceReport](Get-MpPerformanceReport.md#get-mpperformancereport)     
- Performance Analyzer docs



