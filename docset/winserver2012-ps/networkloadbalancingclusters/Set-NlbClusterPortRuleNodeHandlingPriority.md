---
external help file: NLB_Cmdlets.xml
Module Name: NetworkLoadBalancingClusters
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/set-nlbclusterportrulenodehandlingpriority?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NlbClusterPortRuleNodeHandlingPriority

## SYNOPSIS
Sets the host priority of a port rule for a specific Network Load Balancing (NLB) node.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NlbClusterPortRuleNodeHandlingPriority [-Port] <UInt32> [-HostName <String>] -HandlingPriority <Int32>
 -InterfaceName <String> -IP <IPAddress>
```

### UNNAMED_PARAMETER_SET_2
```
Set-NlbClusterPortRuleNodeHandlingPriority -HandlingPriority <Int32> -InputObject <PortRule>
```

## DESCRIPTION
The **Set-NlbClusterPortRuleNodeHandlingPriority** cmdlet sets the host priority of a port rule for a specific Network Load Balancing (NLB) node.
The host priority specifies a unique identifier (ID) for each node.
The node with the lowest numerical priority among the current members of the cluster handles all of the network traffic on the cluster that is not covered by a port rule.
You can override these priorities or provide load balancing for specific ranges of ports by specifying rules.
If a new node joins the cluster and its priority conflicts with another node in the cluster, then the node is not accepted as part of the cluster.
The rest of the cluster will continue to handle the traffic.

This operation changes the configuration on all cluster nodes.
As a result, the NLB cluster will have to restart the convergence process on all nodes to guarantee that configuration changes have been applied on all nodes and that a consistent state is reached.
Any additional operations on the NLB cluster should not be initiated until all cluster nodes have completed the convergence process and are back to the converged state.

ps_nlbc_checkstate_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NlbClusterNode -NodeName node1 | Get-NlbClusterPortRule | Set-NlbClusterPortRuleNodeHandlingPriority -HandlingPriority 3
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout 
--------- -----     -----     ---       --------  ----      --------  ------- 
All       Enabled   0         65535     Both      Single
```

This example changes the handling priority of the given port rule for the node named node1 to 3.
This is applicable for port rules with Single mode.

### EXAMPLE 2
```
PS C:\>Set-NlbClusterPortRuleNodeHandlingPriority -HostName node1 -Interface vlan-3 -IP 255.255.255.255 -Port 80 -HandlingPriority 4
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout 
--------- -----     -----     ---       --------  ----      --------  ------- 
All       Enabled   0         65535     Both      Single
```

This example changes the handling priority of the given port rule for the node named node1 to 4.
This is applicable for port rules with Single mode.

## PARAMETERS

### -HandlingPriority
Specifies the handling priority for the cluster node.
This is only applicable when the filtering mode of the port rule is Single host.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: hp

Required: True
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: hn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IP
Specifies the IP address for the cluster port rule on which the handling priority will be set.

```yaml
Type: IPAddress
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster port rule on which the handling priority will be set.
This is only applicable when the filtering mode for the port rule is Single host.

```yaml
Type: PortRule
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceName
Specifies the interface to which NLB is bound.
This is the interface of the cluster against which this cmdlet is run.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port
Specifies a port number within the port rule on which the node handling priority will be set.
The acceptable values for this parameter are:`0` through `65535`.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.PortRule

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.PortRule

## NOTES

## RELATED LINKS

[Add-NlbClusterPortRule](./Add-NlbClusterPortRule.md)

[Set-NlbClusterPortRule](./Set-NlbClusterPortRule.md)

[Set-NlbClusterPortRuleNodeWeight](./Set-NlbClusterPortRuleNodeWeight.md)

