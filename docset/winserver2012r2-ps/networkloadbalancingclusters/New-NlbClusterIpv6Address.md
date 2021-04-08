---
author: Kateyanne
description: 
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
manager: jasgro
Module Name: NetworkLoadBalancingClusters
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/networkloadbalancingclusters/new-nlbclusteripv6address?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NlbClusterIpv6Address
---

# New-NlbClusterIpv6Address

## SYNOPSIS
Generates an IPv6 address to use with the Network Load Balancing (NLB) cmdlets.

## SYNTAX

```
New-NlbClusterIpv6Address [[-HostName] <String>] [-InterfaceName] <String> [-LinkLocal] [-Global]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-NlbClusterIpv6Address** cmdlet generates IPv6 addresses to create cluster virtual IP addresses or node dedicated IP addresses.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>New-NlbClusterIpv6Address -InterfaceName vlan-3
fe80::b071:3696:dadd:26d4
```

This example returns the applicable IPv6 addresses to be used with the interface named vlan-3 on the local machine.
This address can be used as a dedicated IP address on the node or a virtual IP address on the cluster.

## PARAMETERS

### -Global
Returns only a global IPv6 address.
If this parameter is omitted, then all applicable IPv6 address types are returned.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: G

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostName
Specifies the name of the cluster host against which this cmdlet is run.
If this parameter is omitted or a value of `.` is entered, then the local cluster is assumed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Host, HN, H

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterfaceName
Specifies the interface to which NLB is bound.
This is the interface of the cluster against which this cmdlet is run.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Interface, IN, I

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LinkLocal
Returns only a link local IPv6 address.
If this parameter is omitted, then all applicable IPv6 address types are returned.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: L

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS

[Add-NlbClusterNodeDip](./Add-NlbClusterNodeDip.md)

[Add-NlbClusterVip](./Add-NlbClusterVip.md)

[New-NlbCluster](./New-NlbCluster.md)

