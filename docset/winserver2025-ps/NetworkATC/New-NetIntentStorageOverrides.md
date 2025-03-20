---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 03/14/2025
online version: https://learn.microsoft.com/powershell/module/networkatc/new-netintentstorageoverrides?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetIntentStorageOverrides
---

# New-NetIntentStorageOverrides

## SYNOPSIS
Creates a new instance of network adapter storage overrides which can be used to supply granular values to `Set-NetIntent`.

## SYNTAX

```
New-NetIntentStorageOverrides [-EnableAutomaticIPGeneration <Boolean>] [<CommonParameters>]
```

## DESCRIPTION

The `New-NetIntentStorageOverrides` cmdlet creates a new instance of storage
network adapter override setting. This instance can be used to specify
configuration values for network adapters when using the `Set-NetIntent` cmdlet.

## EXAMPLES

### Example 1

```powershell
New-NetIntentStorageOverrides -EnableAutomaticIPGeneration $true
```

This example creates a new storage override with automatic IP generation enabled.

## PARAMETERS

### -EnableAutomaticIPGeneration

Indicates whether automatic IP generation should be enabled for the network
adapter storage configuration. When set to `$true`, IP addresses will be
automatically generated based on the network settings.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction,
-ErrorVariable, -InformationAction, -InformationVariable, -OutVariable,
-OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.
For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

- [New-NetIntentAdapterPropertyOverrides](New-NetIntentAdapterPropertyOverrides.md)

- [New-NetIntentAdapterRssOverrides](New-NetIntentAdapterRssOverrides.md)

- [New-NetIntentGlobalClusterOverrides](New-NetIntentGlobalClusterOverrides.md)

- [New-NetIntentGlobalProxyOverrides](New-NetIntentGlobalProxyOverrides.md)

- [New-NetIntentQoSPolicyOverrides](New-NetIntentQoSPolicyOverrides.md)

- [New-NetIntentSiteOverrides](New-NetIntentSiteOverrides.md)

- [New-NetIntentSwitchConfigurationOverrides](New-NetIntentSwitchConfigurationOverrides.md)
