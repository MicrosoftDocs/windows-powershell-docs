---
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
online version: 
schema: 2.0.0
title: Get-NlbClusterNodeNetworkInterface
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: C35EB814-5C83-490B-9BF8-4437F7975E3C
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-NlbClusterNodeNetworkInterface

## SYNOPSIS
Retrieves information about interfaces, including information about the Network Load Balancing (NLB) driver, on a host.

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
The **Get-NlbClusterNodeNetworkInterface** cmdlet retrieves information about interfaces, including information about the Network Load Balancing (NLB) driver, on a host.

## EXAMPLES

### EXAMPLE 1
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

This example gets information about all network interfaces on the local node.
The information returned includes whether NLB is bound to that interface and whether that interface is DHCP-enabled.

### EXAMPLE 2
```
PS C:\>Get-NlbClusterNodeNetworkInterface -HostName node1
InterfaceName       : vlan-4 
NlbBound            : True 
Cluster             : cluster1 
DhcpEnabled         : False 
InterfaceIP         : 4.53.4.1 
InterfaceSubnetMask : 255.0.0.0 
ClusterPrimaryIP    : 4.53.100.100 
ClusterSubnetMask   : 255.0.0.0
```

This example gets information about all network interfaces on the node named node1.
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
Specifies the cluster node for which network interface information is retrieved.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Node

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.NetworkInterface

## NOTES

## RELATED LINKS

[New-NlbCluster](./New-NlbCluster.md)

