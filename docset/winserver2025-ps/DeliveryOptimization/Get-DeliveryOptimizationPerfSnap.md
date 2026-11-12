---
external help file: DeliveryOptimizationStatus.psm1-help.xml
Module Name: DeliveryOptimization
ms.date: 11/02/2026
online version: https://learn.microsoft.com/powershell/module/deliveryoptimization/get-deliveryoptimizationperfsnap?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DeliveryOptimizationPerfSnap
---

# Get-DeliveryOptimizationPerfSnap

## SYNOPSIS

Gets a snapshot of Delivery Optimization performance statistics.

## SYNTAX

```
Get-DeliveryOptimizationPerfSnap [<CommonParameters>]
```

## DESCRIPTION

The `Get-DeliveryOptimizationPerfSnap` cmdlet returns a point-in-time view of Delivery
Optimization activity on the local device.

The snapshot includes download and upload totals, file counts, cache and disk usage, CPU and
memory usage, peer and server connection counts, and bandwidth usage. Use
`Get-DeliveryOptimizationPerfSnapThisMonth` to get usage statistics for the current calendar month.

## EXAMPLES

### Example 1: Get the current performance snapshot

```powershell
Get-DeliveryOptimizationPerfSnap
```

This command returns the current Delivery Optimization performance statistics.

### Example 2: Select cache and transfer statistics

```powershell
Get-DeliveryOptimizationPerfSnap |
    Select-Object Files, CacheSizeBytes, TotalBytesDownloaded, TotalBytesUploaded
```

This command displays the file count, cache size, and downloaded and uploaded byte totals.

## PARAMETERS

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

You can't pipe objects to this cmdlet.

## OUTPUTS

### DOPerfSnap

A performance snapshot containing Delivery Optimization activity and resource usage statistics.

## NOTES

The returned values describe the device when the cmdlet runs. They aren't a continuous
performance trace or a historical monthly report.

## RELATED LINKS

[Get-DeliveryOptimizationPerfSnapThisMonth](Get-DeliveryOptimizationPerfSnapThisMonth.md)

[Get-DeliveryOptimizationStatus](Get-DeliveryOptimizationStatus.md)

[Monitor Delivery Optimization](https://learn.microsoft.com/windows/deployment/do/waas-delivery-optimization-monitor)
