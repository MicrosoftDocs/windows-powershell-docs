---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/get-nlbclusternodenetworkinterface?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NlbClusterNodeNetworkInterface
---

# Get-NlbClusterNodeNetworkInterface

## SYNOPSIS
Gets information about interfaces, including information about the NLB driver, on a host.

## SYNTAX

### NonPipeline (Default)
```
Get-NlbClusterNodeNetworkInterface [[-HostName] <String>] [[-InterfaceName] <String>] [<CommonParameters>]
```

### Pipeline
```
Get-NlbClusterNodeNetworkInterface -InputObject <Node[]> [[-InterfaceName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NlbClusterNodeNetworkInterface** cmdlet gets information about interfaces, including information about the Network Load Balancing (NLB) driver, on a host.

## EXAMPLES

### Example 1: Get information about all network interfaces on the local node
```
PS C:\>Get-NlbClusterNodeNetworkInterface
InterfaceName       : vlan-3
NlbBound            : True
Cluster             : cluster1
DhcpEnabled         : False
InterfaceIP         : 3.53.4.1
InterfaceSubnetMask : 255.0.0.0
ClusterPrimaryIP    : 3.53.100.100
ClusterSubnetMask   : 255.0.0.0

InterfaceName       : vlan-2
NlbBound            : False
Cluster             :
DhcpEnabled         : False
InterfaceIP         : 2.53.4.1
InterfaceSubnetMask : 255.0.0.0
ClusterPrimaryIP    :
ClusterSubnetMask   :
```

This command gets information about all network interfaces on the local node.
The information returned includes whether NLB is bound to that interface and whether that interface is DHCP-enabled.

### Example 2: Get information about all network interfaces on the specified node
```
PS C:\>Get-NlbClusterNodeNetworkInterface -HostName "Node01"
InterfaceName       : vlan-4
NlbBound            : True
Cluster             : cluster1
DhcpEnabled         : False
InterfaceIP         : 4.53.4.1
InterfaceSubnetMask : 255.0.0.0
ClusterPrimaryIP    : 4.53.100.100
ClusterSubnetMask   : 255.0.0.0
```

This command gets information about all network interfaces on the node named Node01.
The information returned includes whether NLB is bound to that interface and whether that interface is DHCP-enabled.

## PARAMETERS

### -HostName
Specifies the name of the cluster host against which this cmdlet is run.
If this parameter is omitted or a value of `.` is entered, then the local cluster is assumed.

```yaml
Type: String
Parameter Sets: NonPipeline
Aliases: Host, HN, H

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies an array of cluster nodes for which this cmdlet gets network interface information.

```yaml
Type: Node[]
Parameter Sets: Pipeline
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -InterfaceName
Specifies the interface to which NLB is bound.
This is the interface of the cluster against which this cmdlet is run.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Interface, IN, I

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Node

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.NetworkInterface

## NOTES

## RELATED LINKS

[New-NlbCluster](./New-NlbCluster.md)

