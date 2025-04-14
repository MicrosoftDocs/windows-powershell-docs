---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/set-nlbclusterportrulenodeweight?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NlbClusterPortRuleNodeWeight
---

# Set-NlbClusterPortRuleNodeWeight

## SYNOPSIS
Sets the load weight of a port rule for a specific NLB node.

## SYNTAX

### NonPipeline (Default)
```
Set-NlbClusterPortRuleNodeWeight [-HostName <String>] -InterfaceName <String> -IP <IPAddress> [-Port] <UInt32>
 [-Equal] [-LoadWeight <Int32>] [<CommonParameters>]
```

### Pipeline
```
Set-NlbClusterPortRuleNodeWeight -InputObject <PortRule[]> [-Equal] [-LoadWeight <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NlbClusterPortRuleNodeWeight** cmdlet sets the load weight of a port rule for a specific Network Load Balancing (NLB) node.
The load weight applies only for the Multiple hosts filtering mode.
When using the Multiple hosts filtering mode, the load weight specifies the relative amount of load-balanced network traffic that this node should handle for the associated port rule.
Allowed integer values range from 0 (zero) to 100.
To prevent a host from handling any network traffic, set the load weight to 0 (zero).
The actual fraction of traffic handled by each node is computed as the local load weight divided by the sum of all load weights across the cluster.
Different load weights can be specified for each node in the cluster using the *LoadWeight* parameter.
Or, all nodes can be specified to distribute the network load equally by using the *Equal* parameter instead of the *LoadWeight* parameter.

This operation changes the configuration on all cluster nodes.
As a result, the NLB cluster restarts the convergence process on all nodes to guarantee that configuration changes have been applied on all nodes and that a consistent state is reached.
Any additional operations on the NLB cluster is not initiated until all cluster nodes have completed the convergence process and are back to the converged state.

ps_nlbc_checkstate_remark

## EXAMPLES

### Example 1: Set the weight for all port rules equal to the load weight on all nodes
```
PS C:\>Get-NlbClusterNode | Get-NlbClusterPortRule | Set-NlbClusterPortRuleNodeWeight -Equal
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout
--------- -----     -----     ---       --------  ----      --------  -------
All       Enabled   0         65535     Both      Multiple  Single    0
```

This command sets the weight for all port rules to equal the load weight on all nodes.
This is applicable for port rules using the Multiple hosts.
Note that this has to be set on all cluster nodes to achieve the desired effect.

### Example 2: Set the weight for the specified port rule equal to the load weight on all nodes
```
PS C:\>Get-NlbClusterNode | Get-NlbClusterPortRule -Port 80 | Set-NlbClusterPortRuleNodeWeight -Equal
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout
--------- -----     -----     ---       --------  ----      --------  -------
All       Enabled   0         65535     Both      Multiple  Single    0
All       Enabled   0         65535     Both      Multiple  Single    0
```

This command sets the weight for the specified port rule to equal the load weight on all nodes.
This is applicable for port rules using the Multiple hosts.
Note that this has to be set on all cluster nodes to achieve the desired effect.

### Example 3: Set the weight for the specified port rule equal on a cluster node
```
PS C:\>Get-NlbClusterNode -NodeName "Node001" | Get-NlbClusterPortRule -Port 80 | Set-NlbClusterPortRuleNodeWeight -LoadWeight 25 | Format-List "*"

Cluster          : cluster1
NodeName         : node1
VirtualIPAddress : 255.255.255.255
StartPort        : 0
EndPort          : 65535
Affinity         : Single
FilteringMode    : Multiple
Protocol         : Both
EqualLoad        : True
LoadWeight       : 25
PortState        : Enabled
Priority         :
Timeout          : 0
```

This command sets the weight for the specified port rule on the node named Node001 to 25.
This is applicable for port rules using the Multiple hosts.
Weights have to be set on each node.

## PARAMETERS

### -Equal
Indicates that the cmdlet sets the port rule weight to Equal on the cluster node.
This specifies that all nodes distribute the network load equally.
This parameter is only applicable when the port rule filtering mode is Multiple hosts.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: E

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
Parameter Sets: NonPipeline
Aliases: Host, HN, H

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IP
Specifies the IP address for the cluster port rule on which this cmdlet sets the load weight.

```yaml
Type: IPAddress
Parameter Sets: NonPipeline
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies an array of cluster port rules on which this cmdlet sets the load weight.
This is only applicable when the port rule filtering mode is Multiple hosts.

```yaml
Type: PortRule[]
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

### -LoadWeight
Specifies the load weight for the given port rule to use for this node.
This is only applicable when the port rule filtering mode is Multiple hosts.
The acceptable values for this parameter are: 0 through 100.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: W

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port
Specifies a port number within the port rule on which this cmdlet sets the node load weight.
The acceptable values for this parameter are: 0 through 65535.

```yaml
Type: UInt32
Parameter Sets: NonPipeline
Aliases: P

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.PortRule

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.PortRule

## NOTES

## RELATED LINKS

[Add-NlbClusterPortRule](./Add-NlbClusterPortRule.md)

[Get-NlbClusterPortRule](./Get-NlbClusterPortRule.md)

[Set-NlbClusterPortRule](./Set-NlbClusterPortRule.md)

[Set-NlbClusterPortRuleNodeHandlingPriority](./Set-NlbClusterPortRuleNodeHandlingPriority.md)

