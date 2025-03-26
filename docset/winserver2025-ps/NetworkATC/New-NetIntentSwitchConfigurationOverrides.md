---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 03/14/2025
online version: https://learn.microsoft.com/powershell/module/networkatc/new-netintentswitchconfigurationoverrides?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetIntentSwitchConfigurationOverrides
---

# New-NetIntentSwitchConfigurationOverrides

## SYNOPSIS
Creates a new instance of virtual switch configuration overrides which can be used to supply granular values to `Set-NetIntent`.

## SYNTAX

```
New-NetIntentSwitchConfigurationOverrides [-EnableSoftwareRsc <Boolean>]
 [-DefaultQueueVrssMaxQueuePairs <UInt32>] [-DefaultQueueVrssMinQueuePairs <UInt32>]
 [-DefaultQueueVrssQueueSchedulingMode <UInt32>] [-EnableIov <Boolean>]
 [-EnableEmbeddedTeaming <Boolean>] [-LoadBalancingAlgorithm <String>] [<CommonParameters>]
```

## DESCRIPTION

The `New-NetIntentSwitchConfigurationOverrides` cmdlet creates a new instance of a virtual switch
configuration override that allows you to provide specific configuration values for network intent
settings.

## EXAMPLES

### Example 1

```powershell
$params = @{
    DefaultQueueVrssMaxQueuePairs  = 16
    EnableSoftwareRsc              = $true
    EnableIov                      = $false
}
New-NetIntentSwitchConfigurationOverrides @params
```

This example creates a new switch configuration override with the maximum number of Vrss queue pairs
to `16` while enabling Software RSC and disabling IOV.

## PARAMETERS

### -EnableSoftwareRsc

Indicates whether Software Receive Side Coalescing (RSC) is enabled. When enabled, this feature can
improve network performance by reducing the CPU load associated with processing received packets.

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

### -DefaultQueueVrssMaxQueuePairs

Specifies the maximum number of Virtual RSS (Vrss) queue pairs to be used by default. This parameter
can help optimize network performance by balancing the load across multiple CPU cores.

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

### -DefaultQueueVrssMinQueuePairs

Specifies the minimum number of Virtual RSS (Vrss) queue pairs to be used by default. Setting this
can ensure a minimum level of resource allocation for network traffic processing.

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

### -DefaultQueueVrssQueueSchedulingMode

Defines the scheduling mode for Virtual RSS (Vrss) queues. This parameter can be used to configure
how Virtual RSS queues are scheduled for processing network traffic.

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

### -EnableIov

Indicates whether Input-Output Virtualization (IOV) is enabled. IOV allows VMs to have direct access
to hardware I/O resources, potentially improving performance.

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

### -EnableEmbeddedTeaming

Specifies whether Embedded Teaming is enabled. Embedded Teaming allows multiple network adapters to
be grouped together for redundancy and load balancing.

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

### -LoadBalancingAlgorithm

Determines the load balancing algorithm used for distributing network traffic. This parameter can be
used to select a specific algorithm that best suits the network environment.

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

[New-NetIntentAdapterRssOverrides](New-NetIntentAdapterRssOverrides.md)

[New-NetIntentGlobalClusterOverrides](New-NetIntentGlobalClusterOverrides.md)

[New-NetIntentGlobalProxyOverrides](New-NetIntentGlobalProxyOverrides.md)

[New-NetIntentQoSPolicyOverrides](New-NetIntentQoSPolicyOverrides.md)

[New-NetIntentSiteOverrides](New-NetIntentSiteOverrides.md)

[New-NetIntentStorageOverrides](New-NetIntentStorageOverrides.md)
