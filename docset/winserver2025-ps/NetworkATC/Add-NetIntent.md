---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/networkatc/add-netintent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-NetIntent
---

# Add-NetIntent

## SYNOPSIS
Configures network host using intent based tags for adapters

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

`Add-NetIntent` is used to communicate the default networking configurations required on the host.
Each intent is uniquely identified by the list of physical adapters provided. Which means no two
intents can have overlapping physical nic names.

Intents are supported per cluster or as a standalone host.

- For Standalone **ComputerName** should point to the available DNS host Name. (Ensure that the
  current used of the script has administrator priviliges on the remote machine)
- For Cluster: **ClusterName** should point to the available DNS ClusterName. Cluster intents are
  policies which 'floats' across the cluster and any node which finds compatible (matching names )
  will automatically apply the intended networking configuration on it.
- If **ComputerName** and **ClusterName** are null, clustered hosts will use the name of their
  cluster and standalone hosts will use their own host name.

If you're logged into using a remote session, giving a remote cluster name would very likely result
in a 'double hop issue'. For more information, see
[Understanding Kerberos Double Hop](https://techcommunity.microsoft.com/t5/ask-the-directory-services-team/understanding-kerberos-double-hop/ba-p/395463)

Cluster DNS name is 'floating' and may be actively registered to any of the node's IP address. If
the active IP does not belong to the node this script is being run, then a remote call will be made.
In a remote session, this is a double hop and will fail.

As an alternative, you can try giving `-ClusterName <localhostname>` as the target endpoint. This
will cause the resolution to be forced to the local instance of the cluster. This is different from
calling `-ComputerName <localhostname>`, calling with -ComputerName updates only the local reposity.
Intents in the local repositories are skipped if the ndoe is a part of a cluster.

Once an intent is created, it may not be modified. The only way to re-do is to do a cleanup using
`Clear-NetIntent` and then applying `Add-NetIntent` again.

However, configuration changes like providing override for defaults is possible. This can be
achieved by providing _policy overrides_ (see **AdapterPropertyOverrides**, **QoSPolicyOverrides**,
**AdapterRssOverrides**, and **SwitchOverrides**). These can also be supplied during `Add-NetIntent`
and can also be applied post facto using `Add-NetIntentOverride`.

`Set-NetIntentTracing` can be used to enable / disable tracing for collecting dignostic information
about operations of NetworkAtc

Intent status is retried a few times and then the engine gives up. This would be marked as
**Failed**. You can query the status by running `Get-NetIntentStatus`.

## EXAMPLES

### EXAMPLE 1

```
Add-NetIntent
```

## PARAMETERS

### -AdapterName

A list of physical network adapters on which this intent will be created. If an intent requires
switch creation, one switch will be created. If a switch is created with multiple adapters, a NIC
teaming will be automatically be created.

```yaml
Type: System.String[]
Parameter Sets: ComputerName, Cluster
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdapterPropertyOverrides

{{ Fill AdapterPropertyOverrides Description }}

```yaml
Type: FabricManager.NetAdapterAdvancedConfiguration
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdapterRssPropertyOverrides

{{ Fill AdapterRssPropertyOverrides Description }}

```yaml
Type: FabricManager.RssConfiguration
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterName

The name of the target cluster for the intents.

```yaml
Type: System.String
Parameter Sets: Global
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: Cluster
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Compute

Specifies the intent is for compute.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

The name of the target computer for the intents.

```yaml
Type: System.String
Parameter Sets: ComputerName, Global
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GlobalClusterOverrides

{{ Fill GlobalClusterOverrides Description }}

```yaml
Type: FabricManager.ClusterSettings
Parameter Sets: Global
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GlobalProxyOverrides

{{ Fill GlobalProxyOverrides Description }}

```yaml
Type: FabricManager.WinHttpAdvProxy
Parameter Sets: Global
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Management

Specifies the intent is for management.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementVlan

{{ Fill ManagementVlan Description }}

```yaml
Type: System.Int32
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: -1
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

The name of the intent.

```yaml
Type: System.String
Parameter Sets: ComputerName, Cluster
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PutGlobal

{{ Fill PutGlobal Description }}

```yaml
Type: System.Boolean
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -QoSPolicyOverrides

{{ Fill QoSPolicyOverrides Description }}

```yaml
Type: FabricManager.QoSPolicy
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SiteOverrides

{{ Fill SiteOverrides Description }}

```yaml
Type: FabricManager.SiteConfiguration[]
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipNetworkInterfaceValidation

{{ Fill SkipNetworkInterfaceValidation Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Storage

Specifies the intent is for storage.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageOverrides

{{ Fill StorageOverrides Description }}

```yaml
Type: FabricManager.NetAdapterStorageOverride
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageVlans

{{ Fill StorageVlans Description }}

```yaml
Type: System.Int32[]
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stretch

{{ Fill Stretch Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Switchless

{{ Fill Switchless Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -SwitchPropertyOverrides

{{ Fill SwitchPropertyOverrides Description }}

```yaml
Type: FabricManager.SwitchConfigurationOverride
Parameter Sets: ComputerName, Cluster
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait

{{ Fill Wait Description }}

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

## OUTPUTS

## NOTES

## RELATED LINKS
