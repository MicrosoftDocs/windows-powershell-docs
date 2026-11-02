---
external help file: DeliveryOptimizationStatus.psm1-help.xml
Module Name: DeliveryOptimization
ms.date: 11/02/2026
online version: https://learn.microsoft.com/powershell/module/deliveryoptimization/get-doconfig?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DOConfig
---

# Get-DOConfig

## SYNOPSIS

Gets the local configuration and policies applied to Delivery Optimization.

## SYNTAX

```
Get-DOConfig [<CommonParameters>]
```

## DESCRIPTION

The `Get-DOConfig` cmdlet returns Delivery Optimization configuration values and the provider
that supplies each value. Providers can include Group Policy, mobile device management (MDM),
Windows Settings, administrative configuration, and platform defaults.

The default output includes the download mode and bandwidth limits. Use the **Verbose** common
parameter to return extended configuration, including cache location, device resource requirements,
VPN settings, and scheduled bandwidth restrictions.

## EXAMPLES

### Example 1: Get the current configuration

```powershell
Get-DOConfig
```

This command returns the basic Delivery Optimization configuration and the provider for each value.

### Example 2: Get extended configuration

```powershell
Get-DOConfig -Verbose
```

This command returns extended configuration values in addition to the basic configuration.

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

### DOConfig

Basic configuration values and their providers, returned by default.

### DOExtendedConfig

Basic and extended configuration values and their providers, returned when verbose output is enabled.

## NOTES

Use the provider properties to identify whether a value comes from policy or another configuration
source. `DefaultProvider` indicates a Delivery Optimization platform default.

## RELATED LINKS

[Get-DODownloadMode](Get-DODownloadMode.md)

[Set-DODownloadMode](Set-DODownloadMode.md)

[Monitor Delivery Optimization](https://learn.microsoft.com/windows/deployment/do/waas-delivery-optimization-monitor)
