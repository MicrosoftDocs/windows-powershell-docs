---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 03/14/2025
online version: https://learn.microsoft.com/powershell/module/networkatc/new-netintentsiteoverrides?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetIntentSiteOverrides
---

# New-NetIntentSiteOverrides

## SYNOPSIS
Creates a new instance of site configuration overrides which can be used to supply granular values to `Set-NetIntent`.

## SYNTAX

```
New-NetIntentSiteOverrides [[-StorageVLAN] <UInt16[]>] [[-StretchVLAN] <UInt16[]>]
 [[-ManagementVLAN] <UInt16>] [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION

The `New-NetIntentSiteOverrides` cmdlet creates a new instance of a site override. It specifies
detailed configuration values that can be applied to a network intent using the `Set-NetIntent`
cmdlet. It allows administrators to define VLAN settings for storage, stretch, and management
purposes.

## EXAMPLES

### Example 1

```powershell
New-NetIntentSiteOverrides -Name "MySite" -StorageVLAN 101,102
```

This example configures a site named `MySite` and sets up VLAN IDs `101` and `102` for storage
traffic.

## PARAMETERS

### -StorageVLAN

Specifies the VLAN IDs used for storage traffic. This parameter accepts an array of VLAN IDs.

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StretchVLAN

Specifies the VLAN IDs used for stretch networking. This parameter accepts an array of VLAN IDs.

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementVLAN

Specifies the VLAN ID used for network management traffic. This parameter accepts a single VLAN ID.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Specifies the name of the site configuration. This parameter allows you to assign a unique name
making it easier to reference and manage your network policies.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-NetIntentAdapterPropertyOverrides](New-NetIntentAdapterPropertyOverrides.md)

[New-NetIntentAdapterRssOverrides](New-NetIntentAdapterRssOverrides.md)

[New-NetIntentGlobalClusterOverrides](New-NetIntentGlobalClusterOverrides.md)

[New-NetIntentGlobalProxyOverrides](New-NetIntentGlobalProxyOverrides.md)

[New-NetIntentQoSPolicyOverrides](New-NetIntentQoSPolicyOverrides.md)

[New-NetIntentStorageOverrides](New-NetIntentStorageOverrides.md)

[New-NetIntentSwitchConfigurationOverrides](New-NetIntentSwitchConfigurationOverrides.md)
