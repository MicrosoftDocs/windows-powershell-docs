---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/networkatc/set-netintent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetIntent
---

# Set-NetIntent

## SYNOPSIS
Allows provisioning of override values for given intents

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

All properties inside the override objects are nullable. Only the properties which are not set will
be applied

## EXAMPLES

### Example 1

```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

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

### -AdapterRssOverrides

{{ Fill AdapterRssOverrides Description }}

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

{{ Fill ClusterName Description }}

```yaml
Type: System.String
Parameter Sets: Cluster
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: Global
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

{{ Fill ComputerName Description }}

```yaml
Type: System.String
Parameter Sets: ComputerName, Global
Aliases:

Required: False
Position: 2
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

{{ Fill Name Description }}

```yaml
Type: System.String
Parameter Sets: ComputerName, Cluster
Aliases:

Required: True
Position: 1
Default value: None
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

### -SwitchOverrides

{{ Fill SwitchOverrides Description }}

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

Once the request has been successfully placed, all services will eventually detect and apply the
updated override policies. Use `Get-NetIntentStatus` to see if the current status. It may take
several minutes for policy application.

To force update policy application, use the `Set-NetIntentRetryState` to put a given policy in a
retry pending state in which case the policy will be forcefully applied.

## RELATED LINKS
