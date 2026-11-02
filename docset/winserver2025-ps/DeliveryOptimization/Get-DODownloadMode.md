---
external help file: DeliveryOptimizationStatus.psm1-help.xml
Module Name: DeliveryOptimization
ms.date: 11/02/2026
online version: https://learn.microsoft.com/powershell/module/deliveryoptimization/get-dodownloadmode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DODownloadMode
---

# Get-DODownloadMode

## SYNOPSIS

Gets the current Delivery Optimization download mode.

## SYNTAX

```
Get-DODownloadMode [<CommonParameters>]
```

## DESCRIPTION

The `Get-DODownloadMode` cmdlet returns the currently active Delivery Optimization download
mode on the local device. The mode controls which download sources and peer discovery
options Delivery Optimization uses.

Use `Get-DOConfig` to also see the configuration provider that supplies the download mode.

## EXAMPLES

### Example 1: Get the active download mode

```powershell
Get-DODownloadMode
```

This command returns the active download mode, such as `CdnOnly`, `Lan`, `Group`, `Internet`,
or `Simple`.

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

### DownloadMode

An enumeration value that identifies the active download mode.

## NOTES

The modes that this cmdlet can report aren't limited to the modes accepted by `Set-DODownloadMode`.
A mode can also be configured through Group Policy or MDM.

## RELATED LINKS

[Set-DODownloadMode](Set-DODownloadMode.md)

[Get-DOConfig](Get-DOConfig.md)

[Monitor Delivery Optimization](https://learn.microsoft.com/windows/deployment/do/waas-delivery-optimization-monitor)
