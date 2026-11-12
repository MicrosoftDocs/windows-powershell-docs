---
external help file: Microsoft.Windows.DeliveryOptimization.AdminCommands.dll-Help.xml
Module Name: DeliveryOptimization
ms.date: 11/02/2026
online version: https://learn.microsoft.com/powershell/module/deliveryoptimization/get-deliveryoptimizationloganalysis?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DeliveryOptimizationLogAnalysis
---

# Get-DeliveryOptimizationLogAnalysis

## SYNOPSIS

Analyzes Delivery Optimization logs to summarize downloads and peering efficiency.

## SYNTAX

```
Get-DeliveryOptimizationLogAnalysis [-ListConnections] [[-Path] <String[]>] [-Flush] [<CommonParameters>]
```

## DESCRIPTION

The `Get-DeliveryOptimizationLogAnalysis` cmdlet analyzes Delivery Optimization ETL files.
By default, it summarizes file counts, foreground downloads, files eligible for peering,
files that found or downloaded from peers, and overall and peer-assisted download efficiency.

Use **ListConnections** to get connection details, including peer address, peer type, status
code, bytes sent and received, and file ID.

Use **Path** to analyze saved ETL files. If you omit **Path**, the cmdlet reads the Delivery
Optimization service logs. For the latest trace data, run `Get-DeliveryOptimizationLog -Flush`
before analysis. Flushing stops the service and can interrupt active downloads.

## EXAMPLES

### Example 1: Analyze the local Delivery Optimization logs

```powershell
Get-DeliveryOptimizationLogAnalysis
```

This command summarizes download and peering activity in the default service logs.
Run it from an elevated PowerShell session.

### Example 2: List connections from a saved trace

```powershell
Get-DeliveryOptimizationLogAnalysis -Path 'C:\Logs\DeliveryOptimization.etl' -ListConnections
```

This command returns connection details from the specified ETL file.

## PARAMETERS

### -Flush

Flushes buffered Delivery Optimization trace data before analyzing the logs. This stops the
Delivery Optimization service and can interrupt active downloads. Run with administrator
permissions.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ListConnections

Returns connection details instead of the default summary. Details include destination IP
address, peer type, status code, bytes sent and received, and file ID.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Specifies one or more ETL file paths to analyze. If you omit this parameter, the cmdlet
analyzes the Delivery Optimization service logs. You can pipe paths to this parameter or
provide objects with a **Path** or **PSPath** property.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSPath

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

You can pipe ETL file paths to this cmdlet.

## OUTPUTS

### Microsoft.Windows.DeliveryOptimization.AdminCommands.LogOutput

Analysis results summarizing download activity or listing connection details.

## NOTES

Analysis can take several minutes. Reading the default service logs or using **Flush**
requires an elevated PowerShell session.

## RELATED LINKS

[Get-DeliveryOptimizationLog](Get-DeliveryOptimizationLog.md)

[Enable-DeliveryOptimizationVerboseLogs](Enable-DeliveryOptimizationVerboseLogs.md)

[Monitor Delivery Optimization](https://learn.microsoft.com/windows/deployment/do/waas-delivery-optimization-monitor)
