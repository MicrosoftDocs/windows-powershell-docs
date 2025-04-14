---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 03/14/2025
online version: https://learn.microsoft.com/powershell/module/networkatc/new-netintentqospolicyoverrides?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetIntentQoSPolicyOverrides
---

# New-NetIntentQoSPolicyOverrides

## SYNOPSIS
Creates a new instance of QoS policy overrides which can be used to supply granular values to `Set-NetIntent`.

## SYNTAX

```
New-NetIntentQoSPolicyOverrides [-PriorityValue8021Action_SMB <Byte>]
 [-PriorityValue8021Action_Cluster <Byte>] [-BandwidthPercentage_SMB <Byte>]
 [-BandwidthPercentage_Cluster <Byte>] [-NetDirectPortMatchCondition <Int32>] [<CommonParameters>]
```

## DESCRIPTION

The `New-NetIntentQoSPolicyOverrides` cmdlet creates a new instance of Quality of Service (QoS)
policy overrides. This cmdlet is used to provide specific granular values that can be utilized by
the `Set-NetIntent` cmdlet to define QoS policies for network traffic.

## EXAMPLES

### Example 1

```powershell
New-NetIntentQoSPolicyOverrides -PriorityValue8021Action_SMB 3 -BandwidthPercentage_SMB 30
```

This example creates a new QoS policy override setting the 802.1 priority value for SMB traffic to
`3` with `30%` of the available network bandwidth allocated to SMB traffic.

## PARAMETERS

### -PriorityValue8021Action_SMB

Specifies the 802.1 priority value for SMB traffic.

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

### -PriorityValue8021Action_Cluster

Specifies the 802.1 priority value for Cluster traffic.

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

### -BandwidthPercentage_SMB

Specifies the percentage of allocated bandwidth for the SMB traffic.

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

### -BandwidthPercentage_Cluster

Specifies the percentage of allocated bandwidth for the Cluster traffic.

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

### -NetDirectPortMatchCondition

Specifies the port number used to match NetDirect traffic.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
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
