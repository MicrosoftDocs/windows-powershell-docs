---
external help file: DDVCmdlets.dll-Help.xml
Module Name: Microsoft.DiagnosticDataViewer
online version: https://learn.microsoft.com/powershell/module/microsoft.diagnosticdataviewer/get-diagnosticdata?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DiagnosticData
---

# Get-DiagnosticData

## SYNOPSIS
Fetches historical Windows Diagnostic Data uploaded by this machine.

## SYNTAX

```
Get-DiagnosticData [[-StartTime] <DateTime>] [[-EndTime] <DateTime>] [[-RecordCount] <Int32>]
 [-DiagnosticDataType <Int32>] [-BasicTelemetryOnly] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet fetches historical Windows Diagnostic Data uploaded by this machine.
The total available historical data is limited by the diagnostic data store's configurations.
See 'Set-DiagnosticStoreCapacity' for changes.

## EXAMPLES

### EXAMPLE 1
```
Get-DiagnosticData -StartTime (Get-Date).AddDays(-1) -RecordCount 1
```

Returns first (oldest) diagnostic event since yesterday.
Sample output below.

Name : Microsoft.Windows.Kernel.PnP.DeviceConfig

Timestamp : 11/8/2018 4:52:53 PM

Payload : JSON PAYLOAD

IsBasic : False

DiagnosticDataTypes : {11}

### EXAMPLE 2
```
Get-DiagnosticData -StartTime (Get-Date).AddHours(-12) -EndTime (Get-Date).AddHours(-6) -BasicTelemetryOnly
```

Returns all basic diagnostic events sent between 12 and 6 hours before now.

### EXAMPLE 3
```
Get-DiagnosticData -DiagnosticDataType 11
```

Returns diagnostic events tagged with diagnostic data type ID 11.
See Get-DiagnosticDataTypes for the list of diagnostic data types.

## PARAMETERS

### -StartTime
Query filter parameter.
Specifies start time of the window for the oldest event in the fetched set.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: st, start

Required: False
Position: 0
Default value: 1/1/0001 12:00:00 AM
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -EndTime
Query filter parameter.
Specifies end time of the window for the newest event in the fetched set.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: et, end

Required: False
Position: 1
Default value: 12/31/9999 11:59:59 PM
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RecordCount
Specifies maximum number of events to fetch.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: rc, recCount, c, count

Required: False
Position: 2
Default value: 0
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DiagnosticDataType
Query filter parameter.
Specifies if resultset should only include events having this diagnostic data type.
See Get-DiagnosticDataTypes for data type IDs.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: ddt, dt

Required: False
Position: Named
Default value: -2147483648
Accept pipeline input: False
Accept wildcard characters: False
```

### -BasicTelemetryOnly
Query filter parameter.
Specifies if resultset should only include Basic diagnostic data events.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: basic, basicOnly

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.DateTime
Query filter parameter.
Specifies start time of the window for the oldest event in the fetched set.

### System.DateTime
Query filter parameter.
Specifies end time of the window for the newest event in the fetched set.

### System.Int32
Specifies maximum number of events to fetch.

## OUTPUTS

### DDVCmdlets.Containers.EventRecord
Persisted event record.

## NOTES
Requires Windows 10 version 17134 (1803) or higher

## RELATED LINKS
[About Windows Diagnostic Data](/windows/privacy/windows-diagnostic-data)
