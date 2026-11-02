---
external help file: DeliveryOptimizationStatus.psm1-help.xml
Module Name: DeliveryOptimization
ms.date: 11/02/2026
online version: https://learn.microsoft.com/powershell/module/deliveryoptimization/get-deliveryoptimizationperfsnapthismonth?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DeliveryOptimizationPerfSnapThisMonth
---

# Get-DeliveryOptimizationPerfSnapThisMonth

## SYNOPSIS

Gets Delivery Optimization performance statistics for the current calendar month.

## SYNTAX

```
Get-DeliveryOptimizationPerfSnapThisMonth [<CommonParameters>]
```

## DESCRIPTION

The `Get-DeliveryOptimizationPerfSnapThisMonth` cmdlet returns Delivery Optimization usage
statistics for the current calendar month on the local device.

The statistics include bytes downloaded from HTTP sources, cache servers, LAN peers, and
internet peers, bytes uploaded to peers, foreground and background download rates, and the
start date of the reporting month.

## EXAMPLES

### Example 1: Get this month's usage statistics

```powershell
Get-DeliveryOptimizationPerfSnapThisMonth
```

This command returns Delivery Optimization usage statistics for the current calendar month.

### Example 2: Compare download sources

```powershell
Get-DeliveryOptimizationPerfSnapThisMonth |
    Select-Object MonthStartDate, DownloadHttpBytes, DownloadLanBytes, DownloadInternetBytes
```

This command displays the reporting month's start date and bytes downloaded from HTTP,
LAN peers, and internet peers.

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

### DOMonthlyPerfSnap

A monthly performance snapshot containing transfer totals, download rates, and the reporting
month's start date.

## NOTES

The reporting period is the current calendar month, not the previous 30 days.

## RELATED LINKS

[Get-DeliveryOptimizationPerfSnap](Get-DeliveryOptimizationPerfSnap.md)

[Monitor Delivery Optimization](https://learn.microsoft.com/windows/deployment/do/waas-delivery-optimization-monitor)
