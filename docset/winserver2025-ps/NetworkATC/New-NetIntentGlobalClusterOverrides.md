---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 03/14/2025
online version: https://learn.microsoft.com/powershell/module/networkatc/new-netintentglobalclusteroverrides?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetIntentGlobalClusterOverrides
---

# New-NetIntentGlobalClusterOverrides

## SYNOPSIS
Creates a new instance of cluster setting overrides which can be used to supply granular values to `Add-NetIntent`, `Get-NetIntent`, and `Set-NetIntent`.

## SYNTAX

```
New-NetIntentGlobalClusterOverrides [[-EnableNetworkNaming] <Boolean>]
 [[-EnableLiveMigrationNetworkSelection] <Boolean>]
 [[-EnableVirtualMachineMigrationPerformanceSelection] <Boolean>]
 [[-VirtualMachineMigrationPerformanceOption] <String>] [[-MaximumVirtualMachineMigrations] <Byte>]
 [[-MaximumSMBMigrationBandwidthInGbps] <UInt32>] [<CommonParameters>]
```

## DESCRIPTION

The `New-NetIntentGlobalClusterOverrides` cmdlet creates a new instance of
cluster settings which can be used to supply granular configuration values to
the `Add-NetIntent` and `Set-NetIntent` cmdlets. These settings can also be
retrieved using the `Get-NetIntent` cmdlet.

## EXAMPLES

### Example

```powershell
New-NetIntentGlobalClusterOverrides -EnableNetworkNaming $true -MaximumVirtualMachineMigrations 5
```

This example creates a new instance of a cluster override with network naming
enabled and sets the maximum number of virtual machine migrations to `5`.

## PARAMETERS

### -EnableNetworkNaming

Indicates whether network naming is enabled for the cluster. When set to
`$true`, this setting allows the cluster to use descriptive network names.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableLiveMigrationNetworkSelection

Indicates whether live migration network selection is enabled. When set to
`$true`, this setting allows the cluster to choose the best network for live
migrations.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableVirtualMachineMigrationPerformanceSelection

Indicates whether the selection of virtual machine migration performance options
is enabled. When set to `$true`, this setting allows the selection of
performance options for virtual machine migrations.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualMachineMigrationPerformanceOption

Specifies the performance option for virtual machine migrations.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumVirtualMachineMigrations

Specifies the maximum number of virtual machine migrations that can occur
simultaneously. Setting this to a higher number can increase the load on the
network and hosts.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumSMBMigrationBandwidthInGbps

Specifies the maximum bandwidth in gigabits per second (Gbps) that can be used
for SMB migrations. This setting helps to limit the network bandwidth usage for
migrations.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: 0
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

- [New-NetIntentGlobalProxyOverrides](New-NetIntentGlobalProxyOverrides.md)

- [New-NetIntentQoSPolicyOverrides](New-NetIntentQoSPolicyOverrides.md)

- [New-NetIntentSiteOverrides](New-NetIntentSiteOverrides.md)

- [New-NetIntentStorageOverrides](New-NetIntentStorageOverrides.md)

- [New-NetIntentSwitchConfigurationOverrides](New-NetIntentSwitchConfigurationOverrides.md)
