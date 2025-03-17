---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 03/14/2025
online version: https://learn.microsoft.com/powershell/module/networkatc/add-netintent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-NetIntent
---

# Add-NetIntent

## SYNOPSIS
Configures the network host using intent-based tags for adapters.

## SYNTAX

### ComputerName (Default)

```
Add-NetIntent [[-ComputerName] <String>] -AdapterName <String[]> -Name <String> [-Wait] [-Compute]
 [-Management] [-Storage] [-Switchless] [-Stretch]
 [-AdapterPropertyOverrides <NetAdapterAdvancedConfiguration>] [-QoSPolicyOverrides <QoSPolicy>]
 [-AdapterRssPropertyOverrides <RssConfiguration>]
 [-SwitchPropertyOverrides <SwitchConfigurationOverride>]
 [-StorageOverrides <NetAdapterStorageOverride>] [-SiteOverrides <SiteConfiguration[]>]
 [-StorageVlans <Int32[]>] [-ManagementVlan <Int32>] [-SkipNetworkInterfaceValidation]
 [-PutGlobal <Boolean>] [<CommonParameters>]
```

### Global

```
Add-NetIntent [[-ComputerName] <String>] [-ClusterName <String>] [-Wait]
 [-GlobalProxyOverrides <WinHttpAdvProxy>] [-GlobalClusterOverrides <ClusterSettings>]
 [<CommonParameters>]
```

### Cluster

```
Add-NetIntent -ClusterName <String> -AdapterName <String[]> -Name <String> [-Wait] [-Compute]
 [-Management] [-Storage] [-Switchless] [-Stretch]
 [-AdapterPropertyOverrides <NetAdapterAdvancedConfiguration>] [-QoSPolicyOverrides <QoSPolicy>]
 [-AdapterRssPropertyOverrides <RssConfiguration>]
 [-SwitchPropertyOverrides <SwitchConfigurationOverride>]
 [-StorageOverrides <NetAdapterStorageOverride>] [-SiteOverrides <SiteConfiguration[]>]
 [-StorageVlans <Int32[]>] [-ManagementVlan <Int32>] [-SkipNetworkInterfaceValidation]
 [-PutGlobal <Boolean>] [<CommonParameters>]
```

## DESCRIPTION

The `Add-NetIntent` cmdlet is used to communicate the default networking
configurations required on the host. Each intent is uniquely identified by the
list of physical adapters provided, which means no two intents can have
overlapping physical NIC names. If an intent requires switch creation, one
switch will be created. If a switch is created with multiple adapters, NIC
teaming will be automatically created.

For clustering, intents are supported per cluster or as a standalone host.

- **Standalone**: `$ComputerName` should point to the available DNS host Name.
  Ensure that the current used of the script has administrator privileges on the
  remote machine.

- **Cluster**: `$ClusterName` should point to the available DNS ClusterName.
  Cluster intents are policies which 'floats' across the cluster and any node
  which finds matching names will automatically apply the intended networking
  configuration on it.

- Acceptable intent values are:

  - `Compute`
  - `Management`
  - `Storage`
  - `Stretch`

Once an intent is created, it may not be modified. The only way to override is
to do a cleanup using `Clear-NetIntent` and then applying `Add-NetIntent` again.
However, configuration changes like providing override for defaults are
possible. This can be achieved by applying the override cmdlets. These can also
be supplied when running `Add-NetIntent` and can also be applied post facto
using `Add-NetIntentOverride`.

If `$ComputerName` and `$ClusterName` are null, clustered hosts will use the
name of their cluster for `$Clustername` and standalone hosts will use their own
host name for `$ComputerName`. If you're logged in using a remote session,
providing a remote cluster name would result in a "double hop issue". To learn
more, see
[Understanding Kerberos Double Hop](https://techcommunity.microsoft.com/t5/ask-the-directory-services-team/understanding-kerberos-double-hop/ba-p/395463).

Cluster DNS name is "floating" and may be actively registered to any of the
node's IP address. If the active IP doesn't belong to the node this script is
being run, then a remote call will be made. In a remote session, this is a
double hop and will fail. As an alternative, you can try using
`-ClusterName <localhostname>` as the target endpoint. This will cause the
resolution to be forced to the local instance of the cluster. This is different
from using `-ComputerName <localhostname>` as calling with **ComputerName**
updates only the local reposity. Intents in the local repositories are skipped
if the node is a part of a cluster.

`Set-NetIntentTracing` can be used to enable or disable tracing for collecting
diagnostic information about operations of the NetworkATC module. The intent
status is retried a few times and then the engine gives up. This would be marked
as "Failed" and you can query the status by running `Get-NetIntentStatus`.

## EXAMPLES

### EXAMPLE 1

```powershell
Add-NetIntent –AdapterName "Ethernet0" –ComputerName "Server01" –Name "MyIntent" -Compute
```

This example creates a new `Compute` intent for the standalone device named
`Server01` on network adapter `Ethernet0`.

## PARAMETERS

### -ComputerName

Specifies the computer name of the target host on which the network
intent configuration will be applied. For standalone hosts, use the local
computer name; for scenarios where the script is executed remotely, ensure the
current user has administrative privileges on the target machine.

```yaml
Type: String
Parameter Sets: ComputerName, Global
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterName

Specifies the name of the cluster for which the network intent is being
defined. When used, the intent "floats" across the cluster. Any node with
matching physical adapter names will automatically apply the intended
configuration.

```yaml
Type: String
Parameter Sets: Global
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Cluster
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdapterName

Specifies one or more physical network adapter names on which the network intent will be applied.

```yaml
Type: String[]
Parameter Sets: ComputerName, Cluster
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Defines a unique name that identifies the network intent. Since intents are
uniquely determined by their list of physical adapters, the name is used as an
identifier to ensure that each intent is distinct.

```yaml
Type: String
Parameter Sets: ComputerName, Cluster
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait

When specified, the command will wait for the network configuration commands to
complete or for status confirmation before returning control.

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

### -Compute

Indicates that the network intent includes configuration related to compute workloads.

```yaml
Type: SwitchParameter
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Management

Designates that the network intent includes configuration for management traffic.

```yaml
Type: SwitchParameter
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Storage

Signals that the network intent includes storage-specific settings.

```yaml
Type: SwitchParameter
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Switchless

Indicates that the configuration should be applied without creating a virtual
switch. This mode is used when you want to configure the physical adapters
directly without introducing additional switch constructs.

```yaml
Type: SwitchParameter
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stretch

Enables stretch mode, allowing the network configuration to extend across
multiple physical networks or sites. This option is useful for environments that
require network intents to span more than one location or subnet.

```yaml
Type: SwitchParameter
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdapterPropertyOverrides

Allows you to specify a custom set of advanced property values for the network
adapter(s), overriding the default settings applied by the intent.

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

Provides the ability to supply custom Quality of Service (QoS) policy settings
that override the defaults.

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

### -AdapterRssPropertyOverrides

Allows you to provide custom overrides for Receive Side Scaling (RSS)
configurations on the network adapter(s).

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

### -SwitchPropertyOverrides

Provides custom configuration overrides for virtual switch properties. These
settings allow you to fine-tune the behavior of the virtual switch that might be
created as part of the network intent, replacing the default switch
configurations as needed.

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

Enables custom override settings specific to storage adapter configurations. Use
this parameter to replace default storage network settings with those that
better suit your storage traffic.

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

Allows you to apply site-specific configuration overrides for different physical or logical sites.

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

Specifies an array of VLAN IDs that should be used for storage traffic.

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

Specifies the VLAN ID for management traffic. When set, network management tasks
(administrative traffic) are aligned with the designated VLAN. The default value
of `–1` indicates that no specific VLAN is used unless explicitly defined.

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

### -SkipNetworkInterfaceValidation

If specified, the command bypasses the standard validation checks for network
interfaces. This might be required in environments where non-standard or virtual
interfaces are in use.

```yaml
Type: SwitchParameter
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -GlobalProxyOverrides

Used with global intents, this parameter allows you to override the default HTTP
proxy settings with custom proxy configurations.

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

Allows you to provide cluster-wide configuration overrides that replace the
default cluster settings.

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

### -PutGlobal

Determines whether the network intent should be registered or persisted
globally. When set to `$true` (the default), the intent is applied to the global
repository, making it visible across the cluster. If `$false`, the intent is
only updated locally and not propagated to the global context.

```yaml
Type: Boolean
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: True
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

- [Copy-NetIntent](Copy-NetIntent.md)

- [Get-NetIntent](Get-NetIntent.md)

- [Get-NetIntentStatus](Get-NetIntentStatus.md)

- [Remove-NetIntent](Remove-NetIntent.md)

- [Set-NetIntent](Set-NetIntent.md)
