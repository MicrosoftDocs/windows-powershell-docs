---
external help file: DeliveryOptimizationSettings.psm1-help.xml
Module Name: DeliveryOptimization
ms.date: 11/02/2026
online version: https://learn.microsoft.com/powershell/module/deliveryoptimization/set-domaxforegroundbandwidth?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DOMaxForegroundBandwidth
---

# Set-DOMaxForegroundBandwidth

## SYNOPSIS

Sets the maximum bandwidth for Delivery Optimization foreground downloads.

## SYNTAX

```
Set-DOMaxForegroundBandwidth [[-MaxForegroundBandwidth] <UInt32>] [-Reset] [<CommonParameters>]
```

## DESCRIPTION

The `Set-DOMaxForegroundBandwidth` cmdlet sets an absolute bandwidth limit, in kilobytes per
second (KB/s), for Delivery Optimization foreground downloads on the local device.

Specify **MaxForegroundBandwidth** to set a limit, or **Reset** to restore the default dynamic
bandwidth adjustment. You can't specify both parameters in the same command.

Group Policy or MDM policy can override changes made with this cmdlet.

## EXAMPLES

### Example 1: Limit foreground download bandwidth

```powershell
Set-DOMaxForegroundBandwidth -MaxForegroundBandwidth 10000
```

This command limits Delivery Optimization foreground downloads to 10,000 KB/s.

### Example 2: Restore default foreground bandwidth behavior

```powershell
Set-DOMaxForegroundBandwidth -Reset
```

This command removes the limit set by this cmdlet and restores dynamic bandwidth adjustment,
subject to applicable policies.

## PARAMETERS

### -MaxForegroundBandwidth

Specifies the maximum foreground download bandwidth in KB/s. Specify this parameter or **Reset**,
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

Restores the default dynamic foreground download bandwidth adjustment. Don't specify
**MaxForegroundBandwidth** with this parameter.

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

[Set-DOMaxBackgroundBandwidth](Set-DOMaxBackgroundBandwidth.md)

[Set-DOPercentageMaxForegroundBandwidth](Set-DOPercentageMaxForegroundBandwidth.md)

[Get-DOConfig](Get-DOConfig.md)

[Monitor Delivery Optimization](https://learn.microsoft.com/windows/deployment/do/waas-delivery-optimization-monitor)
