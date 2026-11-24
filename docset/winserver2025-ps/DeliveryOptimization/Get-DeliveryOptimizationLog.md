---
external help file: Microsoft.Windows.DeliveryOptimization.AdminCommands.dll-Help.xml
Module Name: DeliveryOptimization
ms.date: 11/02/2026
online version: https://learn.microsoft.com/powershell/module/deliveryoptimization/get-deliveryoptimizationlog?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DeliveryOptimizationLog
---

# Get-DeliveryOptimizationLog

## SYNOPSIS

Gets Delivery Optimization trace log entries as PowerShell objects.

## SYNTAX

```
Get-DeliveryOptimizationLog [-LevelFilter <UInt32>] [-Provider <ProviderType>] [[-Path] <String[]>]
 [-Flush] [<CommonParameters>]
```

## DESCRIPTION

The `Get-DeliveryOptimizationLog` cmdlet reads Delivery Optimization event trace log (ETL)
files and writes the log entries to the PowerShell pipeline as objects.

Use **Path** to read saved ETL files. If you omit **Path**, the cmdlet reads logs from the
Delivery Optimization service log directory, which requires administrator permissions.

Use **Flush** to flush buffered trace data before reading logs.

## EXAMPLES

### Example 1: Read the local Delivery Optimization logs

```powershell
Get-DeliveryOptimizationLog
```

This command reads the default service log directory. Run it from an elevated PowerShell session.

### Example 2: Read a saved trace file

```powershell
Get-DeliveryOptimizationLog -Path 'C:\Logs\DeliveryOptimization.etl'
```

This command converts entries in the specified ETL file to PowerShell objects.

### Example 3: Export the latest logs to a text file

```powershell
Get-DeliveryOptimizationLog -Flush | Set-Content -Path 'C:\Logs\DeliveryOptimization.txt'
```

This command flushes buffered trace data and saves the log entries as text. The destination
directory must already exist.

## PARAMETERS

### -Flush

Flushes buffered Delivery Optimization trace data before reading the logs. Run with
administrator permissions.

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

### -LevelFilter

Specifies the numeric event trace level filter to apply when reading log entries.

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

### -Path

Specifies one or more ETL file paths to read. Pass paths directly to **Path**. If you omit
this parameter, the cmdlet reads the Delivery Optimization service log directory.

Although the parameter metadata declares pipeline input support by value and by the **Path**
or **PSPath** property, the cmdlet selects and reads files before processing pipeline input.
Piped paths don't select the files to read.

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

### -Provider

Specifies the Delivery Optimization trace provider to read. The accepted values are `Dosvc`
for the Delivery Optimization service provider and `Domgmt` for the management provider.

```yaml
Type: Microsoft.Windows.DeliveryOptimization.AdminCommands.ProviderType
Parameter Sets: (All)
Aliases:
Accepted values: Dosvc, Domgmt

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

### System.String[]

The parameter metadata declares pipeline input support, but piped paths don't select the
files to read. Pass ETL file paths directly to **Path** instead.

## OUTPUTS

### Microsoft.Windows.DeliveryOptimization.AdminCommands.LogOutput

Delivery Optimization trace log entries.

## NOTES

Reading the default service logs or using **Flush** requires an elevated PowerShell session.
Use `Get-DeliveryOptimizationLogAnalysis` to summarize download and peering activity.

## RELATED LINKS

[Get-DeliveryOptimizationLogAnalysis](Get-DeliveryOptimizationLogAnalysis.md)

[Enable-DeliveryOptimizationVerboseLogs](Enable-DeliveryOptimizationVerboseLogs.md)

[Disable-DeliveryOptimizationVerboseLogs](Disable-DeliveryOptimizationVerboseLogs.md)

[Monitor Delivery Optimization](https://learn.microsoft.com/windows/deployment/do/waas-delivery-optimization-monitor)
