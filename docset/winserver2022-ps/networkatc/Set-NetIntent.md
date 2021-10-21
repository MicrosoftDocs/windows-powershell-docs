---
description: Allows provisioning of override values for given intents.
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 10/21/2021
online version: https://docs.microsoft.com/powershell/module/netwnv/set-netintent?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetIntent
---

# Set-NetIntent

## SYNOPSIS
Allows provisioning of override values for given intents.

## SYNTAX

### ComputerName (Default)
```
Set-NetIntent [-Name] <String> [[-ComputerName] <String>]
 [-AdapterPropertyOverrides <NetAdapterAdvancedConfiguration>] [-QoSPolicyOverrides <QoSPolicy>]
 [-AdapterRssOverrides <RssConfiguration>] [-SwitchOverrides <SwitchConfigurationOverride>] [-Wait]
 [<CommonParameters>]
```

### Cluster
```
Set-NetIntent [-Name] <String> [-ClusterName] <String>
 [-AdapterPropertyOverrides <NetAdapterAdvancedConfiguration>] [-QoSPolicyOverrides <QoSPolicy>]
 [-AdapterRssOverrides <RssConfiguration>] [-SwitchOverrides <SwitchConfigurationOverride>] [-Wait]
 [<CommonParameters>]
```

## DESCRIPTION
All properties inside thge override objects are nullable.
Only the properties which are not set will be  applied

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
Type: NetAdapterAdvancedConfiguration
Parameter Sets: (All)
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
Position: 2
Default value: None
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
Position: 2
Default value: None
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
Position: 1
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

### -SwitchOverrides
{{ Fill SwitchOverrides Description }}

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

### -Wait
{{ Fill Wait Description }}

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
Once the request has been successfully placed, all services will eventually detect and appply the  updated override policies.
Use Get-NetIntentStatus to see if the current status.
It may take several minutes for policy application.

To force update policy application, use the Set-NetIntentRetryState to put a given policy in a retry pending state in which case the policy
will be forcefully applied.

## RELATED LINKS
