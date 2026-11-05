---
external help file: DeliveryOptimizationSettings.psm1-help.xml
Module Name: DeliveryOptimization
ms.date: 11/02/2026
online version: https://learn.microsoft.com/powershell/module/deliveryoptimization/set-dodownloadmode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DODownloadMode
---

# Set-DODownloadMode

## SYNOPSIS

Sets the Delivery Optimization download mode.

## SYNTAX

```
Set-DODownloadMode [-downloadMode] <SettableDownloadMode> [<CommonParameters>]
```

## DESCRIPTION

The `Set-DODownloadMode` cmdlet sets the Delivery Optimization download mode on the local device.
The supported modes are `CdnOnly`, `Lan`, and `Internet`.

The download mode controls whether Delivery Optimization uses HTTP sources only or also
exchanges content with peers. Group Policy or MDM policy can override changes made with this cmdlet.

## EXAMPLES

### Example 1: Enable LAN peering

```powershell
Set-DODownloadMode -downloadMode Lan
```

This command configures Delivery Optimization to use HTTP sources and peers on the local network.

### Example 2: Disable peer-to-peer downloads

```powershell
Set-DODownloadMode -downloadMode CdnOnly
```

This command configures HTTP-only downloads without peer-to-peer sharing.

## PARAMETERS

### -downloadMode

Specifies the download mode. The accepted values are:

- `CdnOnly`: Uses HTTP sources without peer-to-peer sharing.
- `Lan`: Allows peer-to-peer sharing with devices on the local network.
- `Internet`: Allows peer-to-peer sharing with devices on the internet.

```yaml
Type: SettableDownloadMode
Parameter Sets: (All)
Aliases:
Accepted values: CdnOnly, Lan, Internet

Required: True
Position: 1
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

### None

You can't pipe objects to this cmdlet.

## OUTPUTS

### None

This cmdlet doesn't return objects.

## NOTES

Run this cmdlet from an elevated PowerShell session. Use `Get-DODownloadMode` to check the
active mode and `Get-DOConfig` to identify its configuration provider.

## RELATED LINKS

[Get-DODownloadMode](Get-DODownloadMode.md)

[Get-DOConfig](Get-DOConfig.md)

[Monitor Delivery Optimization](https://learn.microsoft.com/windows/deployment/do/waas-delivery-optimization-monitor)
