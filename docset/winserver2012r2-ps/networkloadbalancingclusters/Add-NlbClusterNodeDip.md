---
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/networkloadbalancingclusters/add-nlbclusternodedip?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-NlbClusterNodeDip
---

# Add-NlbClusterNodeDip

## SYNOPSIS
Adds a dedicated IP address to a Network Load Balancing (NLB) cluster.

## SYNTAX

### NonPipeline (Default)
```
Add-NlbClusterNodeDip [-IP] <IPAddress> [-SubnetMask <IPAddress>] [-HostName <String>] -InterfaceName <String>
 [<CommonParameters>]
```

### Pipeline
```
Add-NlbClusterNodeDip -InputObject <Node[]> [-IP] <IPAddress> [-SubnetMask <IPAddress>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-NlbClusterNodeDIP** cmdlet adds a dedicated IP address to a Network Load Balancing (NLB) cluster.
NLB references the dedicated IP address to handle both client-to-cluster traffic and other network traffic that must go specifically to the cluster node.

This cmdlet changes the configuration on all cluster nodes.
As a result, the NLB cluster will have to restart the convergence process on all nodes to guarantee that configuration changes have been applied on all nodes and that a consistent state is reached.
Any additional operations on the NLB cluster should not be initiated until all cluster nodes have completed the convergence process and are back to the converged state.

ps_nlbc_checkstate_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NlbClusterNode node2 | Add-NlbClusterNodeDip fe80::b3c4:cc5:64dd:6e62
Node                       IPAddress                  SubnetMask 
----                       ---------                  ---------- 
node2                      fe80::b3c4:cc5:64dd:6e62
```

This example adds the specified dedicated IP address to the cluster node named node2.

### EXAMPLE 2
```
PS C:\>Add-NlbClusterNodeDip -HostName node2 -InterfaceName vlan-3 -IP fe80::b3c4:cc5:64dd:6e62
Node                       IPAddress                  SubnetMask 
----                       ---------                  ---------- 
node2                      fe80::b3c4:cc5:64dd:6e62
```

This example adds the specified dedicated IP address to the cluster node named node2 on the interface named vlan-3.

## PARAMETERS

### -HostName
Specifies the name of the cluster host against which this cmdlet is run.
If this parameter is omitted or a value of `.` is entered, then the local cluster is assumed.

```yaml
Type: String
Parameter Sets: NonPipeline
Aliases: Host, HN, H

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IP
Specifies the dedicated IP address for the new cluster node.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the node of the cluster to which the dedicated IP address is added.

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
Parameter Sets: NonPipeline
Aliases: Interface, IN, I

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetMask
Specifies the subnet mask for the dedicated IP address of the new cluster node.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Node

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.ClusterNodeDip

## NOTES

## RELATED LINKS

[Get-NlbClusterNodeDip](./Get-NlbClusterNodeDip.md)

[Remove-NlbClusterNodeDip](./Remove-NlbClusterNodeDip.md)

[Set-NlbClusterNodeDip](./Set-NlbClusterNodeDip.md)

