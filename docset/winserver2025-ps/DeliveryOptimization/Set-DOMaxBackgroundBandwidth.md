---
external help file: DeliveryOptimizationSettings.psm1-help.xml
Module Name: DeliveryOptimization
ms.date: 11/02/2026
online version: https://learn.microsoft.com/powershell/module/deliveryoptimization/set-domaxbackgroundbandwidth?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DOMaxBackgroundBandwidth
---

# Set-DOMaxBackgroundBandwidth

## SYNOPSIS

Sets the maximum bandwidth for Delivery Optimization background downloads.

## SYNTAX

```
Set-DOMaxBackgroundBandwidth [[-MaxBackgroundBandwidth] <UInt32>] [-Reset] [<CommonParameters>]
```

## DESCRIPTION

The `Set-DOMaxBackgroundBandwidth` cmdlet sets an absolute bandwidth limit, in kilobytes per
second (KB/s), for Delivery Optimization background downloads on the local device.

Specify **MaxBackgroundBandwidth** to set a limit, or **Reset** to restore the default dynamic
bandwidth adjustment. You can't specify both parameters in the same command.

Group Policy or MDM policy can override changes made with this cmdlet.

## EXAMPLES

### Example 1: Limit background download bandwidth

```powershell
Set-DOMaxBackgroundBandwidth -MaxBackgroundBandwidth 5000
```

This command limits Delivery Optimization background downloads to 5,000 KB/s.

### Example 2: Restore default background bandwidth behavior

```powershell
Set-DOMaxBackgroundBandwidth -Reset
```

This command removes the limit set by this cmdlet and restores dynamic bandwidth adjustment,
subject to applicable policies.

## PARAMETERS

### -MaxBackgroundBandwidth

Specifies the maximum background download bandwidth in KB/s. Specify this parameter or **Reset**,
but not both.

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

Restores the default dynamic background download bandwidth adjustment. Don't specify
**MaxBackgroundBandwidth** with this parameter.

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

Run this cmdlet from an elevated PowerShell session. Use `Get-DOConfig` to inspect bandwidth
settings and their configuration providers.

## RELATED LINKS

[Set-DOMaxForegroundBandwidth](Set-DOMaxForegroundBandwidth.md)

[Set-DOPercentageMaxBackgroundBandwidth](Set-DOPercentageMaxBackgroundBandwidth.md)

[Get-DOConfig](Get-DOConfig.md)

[Monitor Delivery Optimization](https://learn.microsoft.com/windows/deployment/do/waas-delivery-optimization-monitor)
