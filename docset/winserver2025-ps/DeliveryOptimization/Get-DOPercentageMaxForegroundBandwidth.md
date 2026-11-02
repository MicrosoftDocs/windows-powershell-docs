---
external help file: DeliveryOptimizationStatus.psm1-help.xml
Module Name: DeliveryOptimization
ms.date: 11/02/2026
online version: https://learn.microsoft.com/powershell/module/deliveryoptimization/get-dopercentagemaxforegroundbandwidth?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DOPercentageMaxForegroundBandwidth
---

# Get-DOPercentageMaxForegroundBandwidth

## SYNOPSIS

Gets the maximum bandwidth percentage for Delivery Optimization foreground downloads.

## SYNTAX

```
Get-DOPercentageMaxForegroundBandwidth [<CommonParameters>]
```

## DESCRIPTION

The `Get-DOPercentageMaxForegroundBandwidth` cmdlet returns the current maximum percentage
of available bandwidth that Delivery Optimization can use for foreground downloads.

The returned value is a percentage, not an absolute transfer rate. Use `Get-DOConfig` to inspect
bandwidth configuration values and their providers.

## EXAMPLES

### Example 1: Get the foreground bandwidth percentage

```powershell
Get-DOPercentageMaxForegroundBandwidth
```

This command returns the configured maximum foreground download bandwidth percentage.

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

### System.Byte

The maximum foreground download bandwidth percentage.

## NOTES

This cmdlet reports the percentage setting. Absolute bandwidth limits and other applicable
policies can also affect the bandwidth used by downloads.

## RELATED LINKS

[Set-DOPercentageMaxForegroundBandwidth](Set-DOPercentageMaxForegroundBandwidth.md)

[Get-DOPercentageMaxBackgroundBandwidth](Get-DOPercentageMaxBackgroundBandwidth.md)

[Get-DOConfig](Get-DOConfig.md)
