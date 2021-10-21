---
description: Configures network host using intent based tags for adapters.
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 10/21/2021
online version: https://docs.microsoft.com/powershell/module/netwnv/add-netintent?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-NetIntent
---

# Add-NetIntent

## SYNOPSIS
Configures network host using intent based tags for adapters.

## SYNTAX

### ComputerName (Default)
```
Add-NetIntent [[-ComputerName] <String>] -AdapterName <String[]> -Name <String> [-Compute] [-Management]
 [-Storage] [-AdapterPropertyOverrides <NetAdapterAdvancedConfiguration>] [-QoSPolicyOverrides <QoSPolicy>]
 [-AdapterRssPropertyOverrides <RssConfiguration>] [-SwitchPropertyOverrides <SwitchConfigurationOverride>]
 [-StorageVlans <Int32[]>] [-ManagementVlan <Int32>] [-SkipNetworkInterfaceValidation] [<CommonParameters>]
```

### Cluster
```
Add-NetIntent [-ClusterName] <String> -AdapterName <String[]> -Name <String> [-Compute] [-Management]
 [-Storage] [-AdapterPropertyOverrides <NetAdapterAdvancedConfiguration>] [-QoSPolicyOverrides <QoSPolicy>]
 [-AdapterRssPropertyOverrides <RssConfiguration>] [-SwitchPropertyOverrides <SwitchConfigurationOverride>]
 [-StorageVlans <Int32[]>] [-ManagementVlan <Int32>] [-SkipNetworkInterfaceValidation] [<CommonParameters>]
```

## DESCRIPTION
--- Introduction ----
Add-NetIntent is used to communicate the default networking configurations required on the host.
Each intent is uniquely identified by the list of physical adapters provided. Which means no two intents can have overlapping physical nic names.


 --- Clustering ---
Intents are supported per cluster or as a standalone host.

- For Standalone $ComputerName should point to the available DNS host Name.
(Ensure that the current used of the script has administrator priviliges on the remote machine)

- For Cluster:  $ClusterName should point to the available DNS ClusterName.
Cluster intents are policies which 'floats' across the cluster and any node which finds
compatible (matching names ) will automatically apply the intended networking configuration on it.

NOTE: If you're logged into using a remote session, giving a remote cluster name would very likely result in a 'double hop issue'
(see https://techcommunity.microsoft.com/t5/ask-the-directory-services-team/understanding-kerberos-double-hop/ba-p/395463)

Cluster DNS name is 'floating' and may be actively registered to any of the node's IP address. If the active IP does not belong to the node this script
is being run, then a remote call will be made. In a remote session, this is a double hop and will fail. As an alternative, you can try
giving " -ClusterName \<localhostname\>" as the target endpoint. This will cause the resolution to be forced to the local instance of the cluster.
This is different from calling " -ComputerName \<localhostname\>", calling with -ComputerName updates only the local reposity.
Intents in the local repositories are skipped if the ndoe is a part of a cluster.


--- Modification / Overrides ---
Once an intent is created, it may not be modified. The only way to re-do is to do a cleanup using Clear-NetIntent and then applying Add-NetIntent again

However, configuration changes like providing override for defaults is possible. This can be achieved by providing 'PolicyOverrides'
(see AdapterPropertyOverrides, QoSPolicyOverrides, AdapterRssOverrides & SwitchOverrides). These can also be supplied during Add-NetIntent and can also be
applied post facto using Add-NetIntentOverride.

--- Tracing ---
Set-NetIntentTracing can be used to enable / disable tracing for collecting dignostic information about operations of NetworkAtc

--- Retries ---
Intent status is retried a few times and then the engine gives up. This would be marked as 'Failed' you can query the status by running Get-NetIntentStatus.

## EXAMPLES

### EXAMPLE 1
```
Add-NetIntent
```

-Storage/Compute/Management (desired intents )
    -AdapterName (list of physical on which this intent will be created on, if an intent requires switch creation, one switch will be created)
            note: if a switch is created with multiple adapters, a NIC teaming will be automatically be created
    -ClusterName/-ComputerName Target for the intents.
See notes for more information on configuring cluster wide intents

## PARAMETERS

### -AdapterName
{{ Fill AdapterName Description }}

```yaml
Type: String[]
Parameter Sets: (All)
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
Type: NetAdapterAdvancedConfiguration
Parameter Sets: (All)
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
Type: RssConfiguration
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterName
{{ Fill ClusterName Description }}

```yaml
Type: String
Parameter Sets: Cluster
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Compute
{{ Fill Compute Description }}

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

### -ComputerName
{{ Fill ComputerName Description }}

```yaml
Type: String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Management
{{ Fill Management Description }}

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

### -ManagementVlan
{{ Fill ManagementVlan Description }}

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: -1
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
{{ Fill Name Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -QoSPolicyOverrides
{{ Fill QoSPolicyOverrides Description }}

```yaml
Type: QoSPolicy
Parameter Sets: (All)
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Storage
{{ Fill Storage Description }}

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

### -StorageVlans
{{ Fill StorageVlans Description }}

```yaml
Type: Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SwitchPropertyOverrides
{{ Fill SwitchPropertyOverrides Description }}

```yaml
Type: SwitchConfigurationOverride
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
