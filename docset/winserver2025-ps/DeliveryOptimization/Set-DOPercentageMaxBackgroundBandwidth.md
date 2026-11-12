---
external help file: DeliveryOptimizationSettings.psm1-help.xml
Module Name: DeliveryOptimization
ms.date: 11/02/2026
online version: https://learn.microsoft.com/powershell/module/deliveryoptimization/set-dopercentagemaxbackgroundbandwidth?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DOPercentageMaxBackgroundBandwidth
---

# Set-DOPercentageMaxBackgroundBandwidth

## SYNOPSIS

Sets the maximum bandwidth percentage for Delivery Optimization background downloads.

## SYNTAX

```
Set-DOPercentageMaxBackgroundBandwidth [[-MaxBackgroundBandwidthPercentage] <UInt32>] [-Reset]
 [<CommonParameters>]
```

## DESCRIPTION

The `Set-DOPercentageMaxBackgroundBandwidth` cmdlet limits Delivery Optimization background
downloads to a percentage of available bandwidth on the local device.

Specify **MaxBackgroundBandwidthPercentage** to set a percentage, or **Reset** to restore the
default of 45 percent. You can't specify both parameters in the same command.

Group Policy or MDM policy can override changes made with this cmdlet.

## EXAMPLES

### Example 1: Limit background downloads to 30 percent

```powershell
Set-DOPercentageMaxBackgroundBandwidth -MaxBackgroundBandwidthPercentage 30
```

This command limits background download bandwidth to 30 percent of available bandwidth.

### Example 2: Restore the default percentage

```powershell
Set-DOPercentageMaxBackgroundBandwidth -Reset
```

This command restores the default background download bandwidth percentage, subject to
applicable policies.

## PARAMETERS

### -MaxBackgroundBandwidthPercentage

Specifies the maximum percentage of available bandwidth for background downloads.
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

Restores the default background download bandwidth percentage of 45 percent. Don't specify
**MaxBackgroundBandwidthPercentage** with this parameter.

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
`Get-DOPercentageMaxBackgroundBandwidth` to check the percentage setting and `Get-DOConfig` to
inspect applicable configuration providers.

## RELATED LINKS

[Get-DOPercentageMaxBackgroundBandwidth](Get-DOPercentageMaxBackgroundBandwidth.md)

[Set-DOPercentageMaxForegroundBandwidth](Set-DOPercentageMaxForegroundBandwidth.md)

[Set-DOMaxBackgroundBandwidth](Set-DOMaxBackgroundBandwidth.md)

[Monitor Delivery Optimization](https://learn.microsoft.com/windows/deployment/do/waas-delivery-optimization-monitor)
