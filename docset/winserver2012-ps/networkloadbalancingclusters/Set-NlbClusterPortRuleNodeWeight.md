---
external help file: NLB_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 2750FC48-A482-4589-9D63-D697615DC560
manager: dansimp
---

# Set-NlbClusterPortRuleNodeWeight

## SYNOPSIS
Sets the load weight of a port rule for a specific Network Load Balancing (NLB) node.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NlbClusterPortRuleNodeWeight [-Port] <UInt32> [-Equal] [-HostName <String>] [-LoadWeight <Nullable>]
 -InterfaceName <String> -IP <IPAddress>
```

### UNNAMED_PARAMETER_SET_2
```
Set-NlbClusterPortRuleNodeWeight [-Equal] [-LoadWeight <Nullable>] -InputObject <PortRule>
```

## DESCRIPTION
The **Set-NlbClusterPortRuleNodeWeight** cmdlet sets the load weight of a port rule for a specific Network Load Balancing (NLB) node.
The load weight applies only for the Multiple hosts filtering mode.
When using the Multiple hosts filtering mode, the load weight specifies the relative amount of load-balanced network traffic that this node should handle for the associated port rule.
Allowed values range from `0` (zero) to `100`.
To prevent a host from handling any network traffic, set the load weight to `0` (zero).
The actual fraction of traffic handled by each node is computed as the local load weight divided by the sum of all load weights across the cluster.
Different load weights can be specified for each node in the cluster using the **LoadWeight** parameter.
Or, all nodes can be specified to distribute the network load equally by using the **Equal** parameter instead of the **LoadWeight** parameter.

This operation changes the configuration on all cluster nodes.
As a result, the NLB cluster will have to restart the convergence process on all nodes to guarantee that configuration changes have been applied on all nodes and that a consistent state is reached.
Any additional operations on the NLB cluster should not be initiated until all cluster nodes have completed the convergence process and are back to the converged state.

ps_nlbc_checkstate_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NlbClusterNode | Get-NlbClusterPortRule | Set-NlbClusterPortRuleNodeWeight -Equal
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout 
--------- -----     -----     ---       --------  ----      --------  ------- 
All       Enabled   0         65535     Both      Multiple  Single    0
```

This example sets the weight for all port rules to equal the load weight on all nodes.
This is applicable for port rules using the Multiple hosts.
Note that this has to be set on all cluster nodes to achieve the desired effect.

### EXAMPLE 2
```
PS C:\>Get-NlbClusterNode | Get-NlbClusterPortRule -Port 80 | Set-NlbClusterPortRuleNodeWeight -Equal
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout 
--------- -----     -----     ---       --------  ----      --------  ------- 
All       Enabled   0         65535     Both      Multiple  Single    0 
All       Enabled   0         65535     Both      Multiple  Single    0
```

This example sets the weight for the specified port rule to equal the load weight on all nodes.
This is applicable for port rules using the Multiple hosts.
Note that this has to be set on all cluster nodes to achieve the desired effect.

### EXAMPLE 3
```
PS C:\>Get-NlbClusterNode -NodeName node1 | Get-NlbClusterPortRule -Port 80 | Set-NlbClusterPortRuleNodeWeight -LoadWeight 25 | Format-List *
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

This example sets the weight for the specified port rule on the node named node1 to 25.
This is applicable for port rules using the Multiple hosts.
Note that the weights have to be set on each node.

## PARAMETERS

### -Equal
Sets the port rule weight to Equal on the cluster node.
This specifies that all nodes distribute the network load equally.
This parameter is only applicable when the port rule filtering mode is Multiple hosts.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: hn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IP
Specifies the IP address for the cluster port rule on which the load weight will be set.

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
Specifies the cluster port rule on which the load weight will be set.
This is only applicable when the port rule filtering mode is Multiple hosts.

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

### -LoadWeight
Specifies the load weight for the given port rule to use for this node.
This is only applicable when the port rule filtering mode is Multiple hosts.
The acceptable values for this parameter are:`0` through `100`.

```yaml
Type: Nullable
Parameter Sets: (All)
Aliases: w

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port
Specifies a port number within the port rule on which the node load weight will be set.
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

[Get-NlbClusterPortRule](./Get-NlbClusterPortRule.md)

[Set-NlbClusterPortRule](./Set-NlbClusterPortRule.md)

[Set-NlbClusterPortRuleNodeHandlingPriority](./Set-NlbClusterPortRuleNodeHandlingPriority.md)

