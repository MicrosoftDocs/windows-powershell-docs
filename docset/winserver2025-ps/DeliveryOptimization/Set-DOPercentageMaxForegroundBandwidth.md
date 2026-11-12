---
external help file: DeliveryOptimizationSettings.psm1-help.xml
Module Name: DeliveryOptimization
ms.date: 11/02/2026
online version: https://learn.microsoft.com/powershell/module/deliveryoptimization/set-dopercentagemaxforegroundbandwidth?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DOPercentageMaxForegroundBandwidth
---

# Set-DOPercentageMaxForegroundBandwidth

## SYNOPSIS

Sets the maximum bandwidth percentage for Delivery Optimization foreground downloads.

## SYNTAX

```
Set-DOPercentageMaxForegroundBandwidth [[-MaxForegroundBandwidthPercentage] <UInt32>] [-Reset]
 [<CommonParameters>]
```

## DESCRIPTION

The `Set-DOPercentageMaxForegroundBandwidth` cmdlet limits Delivery Optimization foreground
downloads to a percentage of available bandwidth on the local device.

Specify **MaxForegroundBandwidthPercentage** to set a percentage, or **Reset** to restore the
default of 90 percent. You can't specify both parameters in the same command.

Group Policy or MDM policy can override changes made with this cmdlet.

## EXAMPLES

### Example 1: Limit foreground downloads to 80 percent

```powershell
Set-DOPercentageMaxForegroundBandwidth -MaxForegroundBandwidthPercentage 80
```

This command limits foreground download bandwidth to 80 percent of available bandwidth.

### Example 2: Restore the default percentage

```powershell
Set-DOPercentageMaxForegroundBandwidth -Reset
```

This command restores the default foreground download bandwidth percentage, subject to
applicable policies.

## PARAMETERS

### -MaxForegroundBandwidthPercentage

Specifies the maximum percentage of available bandwidth for foreground downloads.
Accepted values are `0` through `100`. Specify this parameter or **Reset**, but not both.

```yaml
Type: System.Nullable`1[System.UInt32]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Reset

Restores the default foreground download bandwidth percentage of 90 percent. Don't specify
**MaxForegroundBandwidthPercentage** with this parameter.

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

This cmdlet doesn't return objects.

## NOTES

Run this cmdlet from an elevated PowerShell session. Use
`Get-DOPercentageMaxForegroundBandwidth` to check the percentage setting and `Get-DOConfig` to
inspect applicable configuration providers.

## RELATED LINKS

[Get-DOPercentageMaxForegroundBandwidth](Get-DOPercentageMaxForegroundBandwidth.md)

[Set-DOPercentageMaxBackgroundBandwidth](Set-DOPercentageMaxBackgroundBandwidth.md)

[Set-DOMaxForegroundBandwidth](Set-DOMaxForegroundBandwidth.md)

[Monitor Delivery Optimization](https://learn.microsoft.com/windows/deployment/do/waas-delivery-optimization-monitor)
