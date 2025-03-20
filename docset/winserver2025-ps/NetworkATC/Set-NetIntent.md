---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 03/14/2025
online version: https://learn.microsoft.com/powershell/module/networkatc/set-netintent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetIntent
---

# Set-NetIntent

## SYNOPSIS
Allows provisioning of override values for the given network intent.

## SYNTAX

### ComputerName (Default)

```
Set-NetIntent [-Name] <String> [[-ComputerName] <String>]
 [-AdapterPropertyOverrides <NetAdapterAdvancedConfiguration>] [-QoSPolicyOverrides <QoSPolicy>]
 [-AdapterRssOverrides <RssConfiguration>] [-SwitchOverrides <SwitchConfigurationOverride>]
 [-StorageOverrides <NetAdapterStorageOverride>] [-SiteOverrides <SiteConfiguration[]>]
 [-StorageVlans <Int32[]>] [-ManagementVlan <Int32>] [-Wait] [<CommonParameters>]
```

### Cluster

```
Set-NetIntent [-Name] <String> [-ClusterName] <String>
 [-AdapterPropertyOverrides <NetAdapterAdvancedConfiguration>] [-QoSPolicyOverrides <QoSPolicy>]
 [-AdapterRssOverrides <RssConfiguration>] [-SwitchOverrides <SwitchConfigurationOverride>]
 [-StorageOverrides <NetAdapterStorageOverride>] [-SiteOverrides <SiteConfiguration[]>]
 [-StorageVlans <Int32[]>] [-ManagementVlan <Int32>] [-Wait] [<CommonParameters>]
```

### Global

```
Set-NetIntent [[-ComputerName] <String>] [[-ClusterName] <String>]
 [-GlobalProxyOverrides <WinHttpAdvProxy>] [-GlobalClusterOverrides <ClusterSettings>] [-Wait]
 [<CommonParameters>]
```

## DESCRIPTION

The `Set-NetIntent` cmdlet allows provisioning of override values for given
network intents. All properties inside the override objects are nullable,
meaning only the properties which are set will be applied.

## EXAMPLES

### Example 1

```powershell
$adapterOverrides = @{
    JumboPacket = 9000
    InterruptModeration = "Enabled"
}
$qosOverrides = @{
    Name = "HighPriority"
    Priority = 1
    BandwidthPercentage = 50
}
$params = @{
    Name                     = "MyIntent"
    ComputerName             = "Server01"
    AdapterPropertyOverrides = $adapterOverrides
    QoSPolicyOverrides       = $qosOverrides
}
Set-NetIntent @params
```

This example sets the network intent named `MyIntent` on the computer `Server01`
with specified adapter property overrides and QoS policy overrides.

## PARAMETERS

### -Name

Specifies the name of the network intent to be set.

```yaml
Type: String
Parameter Sets: ComputerName, Cluster
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Specifies the name of the computer on which the network intent should be set.

```yaml
Type: String
Parameter Sets: ComputerName, Global
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterName

Specifies the name of the cluster on which the network intent should be set.

```yaml
Type: String
Parameter Sets: Cluster
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Global
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdapterPropertyOverrides

Specifies the overrides for network adapter properties.

```yaml
Type: NetAdapterAdvancedConfiguration
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -QoSPolicyOverrides

Specifies the overrides for Quality of Service (QoS) policies.

```yaml
Type: QoSPolicy
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdapterRssOverrides

Specifies the overrides for Receive Side Scaling (RSS) configuration on network adapters.

```yaml
Type: RssConfiguration
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SwitchOverrides

Specifies the overrides for network switch configuration.

```yaml
Type: SwitchConfigurationOverride
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageOverrides

Specifies the overrides for storage-related network adapter properties.

```yaml
Type: NetAdapterStorageOverride
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SiteOverrides

Specifies the overrides for site configuration.

```yaml
Type: SiteConfiguration[]
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageVlans

Specifies the VLANs for storage networks.

```yaml
Type: Int32[]
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementVlan

Specifies the VLAN for management traffic.

```yaml
Type: Int32
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: -1
Accept pipeline input: False
Accept wildcard characters: False
```

### -GlobalProxyOverrides

Specifies the global overrides for proxy settings.

```yaml
Type: WinHttpAdvProxy
Parameter Sets: Global
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GlobalClusterOverrides

Specifies the global overrides for cluster settings.

```yaml
Type: ClusterSettings
Parameter Sets: Global
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait

Indicates that the cmdlet should wait for the operation to complete before
returning control to the command line.

```yaml
Type: SwitchParameter
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

Once the request has been successfully placed, all services will eventually
detect and apply the updated override policies. Use `Get-NetIntentStatus` to see
the current status. This may take several minutes to retrieve.

To force policy updates, use the `Set-NetIntentRetryState` to put a given policy
in a retry pending state in which case the policy will be forcefully applied.

## RELATED LINKS

- [Add-NetIntent](Add-NetIntent.md)

- [Copy-NetIntent](Copy-NetIntent.md)

- [Get-NetIntent](Get-NetIntent.md)

- [Get-NetIntentStatus](Get-NetIntentStatus.md)

- [Remove-NetIntent](Remove-NetIntent.md)
