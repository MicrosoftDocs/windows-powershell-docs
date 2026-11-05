---
external help file: DeliveryOptimizationStatus.psm1-help.xml
Module Name: DeliveryOptimization
ms.date: 11/02/2026
online version: https://learn.microsoft.com/powershell/module/deliveryoptimization/get-dopercentagemaxbackgroundbandwidth?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DOPercentageMaxBackgroundBandwidth
---

# Get-DOPercentageMaxBackgroundBandwidth

## SYNOPSIS

Gets the maximum bandwidth percentage for Delivery Optimization background downloads.

## SYNTAX

```
Get-DOPercentageMaxBackgroundBandwidth [<CommonParameters>]
```

## DESCRIPTION

The `Get-DOPercentageMaxBackgroundBandwidth` cmdlet returns the current maximum percentage
of available bandwidth that Delivery Optimization can use for background downloads.

The returned value is a percentage, not an absolute transfer rate. Use `Get-DOConfig` to inspect
bandwidth configuration values and their providers.

## EXAMPLES

### Example 1: Get the background bandwidth percentage

```powershell
Get-DOPercentageMaxBackgroundBandwidth
```

This command returns the configured maximum background download bandwidth percentage.

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

The maximum background download bandwidth percentage.

## NOTES

This cmdlet reports the percentage setting. Absolute bandwidth limits and other applicable
policies can also affect the bandwidth used by downloads.

## RELATED LINKS

[Set-DOPercentageMaxBackgroundBandwidth](Set-DOPercentageMaxBackgroundBandwidth.md)

[Get-DOPercentageMaxForegroundBandwidth](Get-DOPercentageMaxForegroundBandwidth.md)

[Get-DOConfig](Get-DOConfig.md)
