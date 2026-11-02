---
external help file: DeliveryOptimizationVerboseLogs.psm1-help.xml
Module Name: DeliveryOptimization
ms.date: 11/02/2026
online version: https://learn.microsoft.com/powershell/module/deliveryoptimization/enable-deliveryoptimizationverboselogs?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-DeliveryOptimizationVerboseLogs
---

# Enable-DeliveryOptimizationVerboseLogs

## SYNOPSIS

Enables verbose logging for Delivery Optimization.

## SYNTAX

```
Enable-DeliveryOptimizationVerboseLogs [-Force] [<CommonParameters>]
```

## DESCRIPTION

The `Enable-DeliveryOptimizationVerboseLogs` cmdlet enables verbose Delivery Optimization
tracing and increases the log file and log folder size limits for troubleshooting.

If the Delivery Optimization service is running, the cmdlet prompts to restart it so the changes
take effect. Restarting the service interrupts active downloads. If you decline the restart,
the changes take effect the next time the service starts.

Use `Disable-DeliveryOptimizationVerboseLogs` when you finish collecting diagnostic logs.

## EXAMPLES

### Example 1: Enable verbose logging

```powershell
Enable-DeliveryOptimizationVerboseLogs
```

This command enables verbose logging and prompts to restart the service if it's running.

### Example 2: Enable verbose logging without a restart prompt

```powershell
Enable-DeliveryOptimizationVerboseLogs -Force
```

This command enables verbose logging and restarts the running service without prompting.
The restart interrupts active downloads.

## PARAMETERS

### -Force

Restarts the Delivery Optimization service without prompting if it's running, so the logging
changes take effect immediately. The restart interrupts active downloads.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

You can't pipe objects to this cmdlet.

## OUTPUTS

### None

This cmdlet doesn't return objects. It displays logging configuration status in the console.

## NOTES

Run this cmdlet from an elevated PowerShell session. Verbose logging generates additional
diagnostic data and uses more disk space than normal logging.

## RELATED LINKS

[Disable-DeliveryOptimizationVerboseLogs](Disable-DeliveryOptimizationVerboseLogs.md)

[Get-DeliveryOptimizationLog](Get-DeliveryOptimizationLog.md)

[Monitor Delivery Optimization](https://learn.microsoft.com/windows/deployment/do/waas-delivery-optimization-monitor)
