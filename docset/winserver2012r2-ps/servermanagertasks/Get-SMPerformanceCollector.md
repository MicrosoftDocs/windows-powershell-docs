---
external help file: ServerManagerTasks.cdxml-help.xml
Module Name: ServerManagerTasks
online version: 
schema: 2.0.0
title: Get-SMPerformanceCollector
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: CB5682DE-A40F-4987-BC5B-C4B57F15D352
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-SMPerformanceCollector

## SYNOPSIS
Gets the state of the performance data collector set.

## SYNTAX

```
Get-SMPerformanceCollector -CollectorName <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SMPerformanceCollector** cmdlet gets the state of a data collector set in the Performance Log Analyzer (PLA).
A data collector set groups multiple data collection points, such as performance counters or events, into a single component.
The result returned by this cmdlet is either `Running` or `Stopped`.

## EXAMPLES

### Example 1: Get the Server Manager performance data collector set state
```
PS C:\>Get-SMPerformanceCollector -CollectorName 'Server Manager Performance Monitor'
Running
```

This command gets the state of the performance data collector for Server Manager, 'Server Manager Performance Monitor'.
If performance data collection is turned on, the result returned by this command is `Running`.
If performance data collection is turned off, the result is `Stopped`.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CollectorName
Specifies a data collector set in PLA.
The data collector set for Server Manager is 'Server Manager Performance Monitor'.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Byte

## NOTES

## RELATED LINKS

[Start-SMPerformanceCollector](./Start-SMPerformanceCollector.md)

[Stop-SMPerformanceCollector](./Stop-SMPerformanceCollector.md)

