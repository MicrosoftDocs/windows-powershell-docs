---
external help file: DeliveryOptimizationVerboseLogs.psm1-help.xml
Module Name: DeliveryOptimization
ms.date: 11/02/2026
online version: https://learn.microsoft.com/powershell/module/deliveryoptimization/disable-deliveryoptimizationverboselogs?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-DeliveryOptimizationVerboseLogs
---

# Disable-DeliveryOptimizationVerboseLogs

## SYNOPSIS

Disables verbose logging for Delivery Optimization.

## SYNTAX

```
Disable-DeliveryOptimizationVerboseLogs [-Force] [<CommonParameters>]
```

## DESCRIPTION

The `Disable-DeliveryOptimizationVerboseLogs` cmdlet removes the verbose tracing configuration
and log size overrides set by `Enable-DeliveryOptimizationVerboseLogs`.

If the Delivery Optimization service is running, the cmdlet prompts to restart it so the changes
take effect. Restarting the service interrupts active downloads. If you decline the restart,
the changes take effect the next time the service starts.

## EXAMPLES

### Example 1: Disable verbose logging

```powershell
Disable-DeliveryOptimizationVerboseLogs
```

This command disables verbose logging and prompts to restart the service if it's running.

### Example 2: Disable verbose logging without a restart prompt

```powershell
Disable-DeliveryOptimizationVerboseLogs -Force
```

This command disables verbose logging and restarts the running service without prompting.
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

Run this cmdlet from an elevated PowerShell session.

## RELATED LINKS

[Enable-DeliveryOptimizationVerboseLogs](Enable-DeliveryOptimizationVerboseLogs.md)

[Get-DeliveryOptimizationLog](Get-DeliveryOptimizationLog.md)

[Monitor Delivery Optimization](https://learn.microsoft.com/windows/deployment/do/waas-delivery-optimization-monitor)
