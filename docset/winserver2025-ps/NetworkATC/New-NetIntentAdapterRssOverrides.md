---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 03/14/2025
online version: https://learn.microsoft.com/powershell/module/networkatc/new-netintentadapterrssoverrides?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetIntentAdapterRssOverrides
---

# New-NetIntentAdapterRssOverrides

## SYNOPSIS
Creates a new instance of RSS overrides which can be used to supply granular values to `Set-NetIntent`.

## SYNTAX

```
New-NetIntentAdapterRssOverrides [-RssEnabled <Boolean>] [-BaseProcessorGroup <UInt16>]
 [-BaseProcessorNumber <Byte>] [-MaxProcessorGroup <UInt16>] [-MaxProcessorNumber <Byte>]
 [-MaxProcessors <UInt32>] [-Profile <String>] [<CommonParameters>]
```

## DESCRIPTION

The `New-NetIntentAdapterRssOverrides` cmdlet creates a new instance of Receive Side Scaling (RSS)
overrides. These overrides allow you to specify detailed processor and RSS configuration settings,
which can be applied using the `Set-NetIntent` cmdlet.

## EXAMPLES

### Example

```powershell
$params = @{
    RssEnabled          = $true
    BaseProcessorGroup  = 0
    BaseProcessorNumber = 2
    MaxProcessorGroup   = 0
    MaxProcessorNumber  = 8
    MaxProcessors       = 4
}
New-NetIntentAdapterRssOverrides @params
```

This example demonstrates how to create a new RSS override instance with RSS enabled. It specifies
the base processor group and number, as well as the maximum processor group and number.
Additionally, it sets the total number of processors to be used for RSS to `4`.

## PARAMETERS

### -RssEnabled

Specifies whether RSS should be enabled. When RSS is enabled, network traffic is distributed across
multiple processors to improve performance.

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

### -BaseProcessorGroup

Specifies the base processor group. This is the starting group number for the processors that will
be used by RSS.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -BaseProcessorNumber

Specifies the base processor number within the base processor group in bytes. This is the starting
processor number within the base group for RSS.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxProcessorGroup

Specifies the maximum processor group. This defines the last group number that will be used by RSS.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxProcessorNumber

Specifies the maximum processor number within the maximum processor group. This defines the last
processor number within the maximum group that will be used by RSS.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxProcessors

Specifies the total number of processors that RSS can use. This limits the number of processors that
can handle network traffic.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile

Specifies the profile to be used for the RSS settings. This can be a custom profile name that
contains predefined RSS settings.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

[New-NetIntentGlobalClusterOverrides](New-NetIntentGlobalClusterOverrides.md)

[New-NetIntentGlobalProxyOverrides](New-NetIntentGlobalProxyOverrides.md)

[New-NetIntentQoSPolicyOverrides](New-NetIntentQoSPolicyOverrides.md)

[New-NetIntentSiteOverrides](New-NetIntentSiteOverrides.md)

[New-NetIntentStorageOverrides](New-NetIntentStorageOverrides.md)

[New-NetIntentSwitchConfigurationOverrides](New-NetIntentSwitchConfigurationOverrides.md)
