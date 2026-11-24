---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/set-nlbclusterportrulenodehandlingpriority?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NlbClusterPortRuleNodeHandlingPriority
---

# Set-NlbClusterPortRuleNodeHandlingPriority

## SYNOPSIS
Sets the host priority of a port rule for a specific Network Load Balancing (NLB) node.

## SYNTAX

### NonPipeline (Default)
```
Set-NlbClusterPortRuleNodeHandlingPriority [-HostName <String>] -InterfaceName <String> -IP <IPAddress>
 [-Port] <UInt32> -HandlingPriority <Int32> [<CommonParameters>]
```

### Pipeline
```
Set-NlbClusterPortRuleNodeHandlingPriority -InputObject <PortRule[]> -HandlingPriority <Int32>
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-NlbClusterPortRuleNodeHandlingPriority** cmdlet sets the host priority of a port rule for a specific Network Load Balancing (NLB) node.
The host priority specifies a unique identifier (ID) for each node.
The node with the lowest numerical priority among the current members of the cluster handles all of the network traffic on the cluster that is not covered by a port rule.
You can override these priorities or provide load balancing for specific ranges of ports by specifying rules.
If a new node joins the cluster and its priority conflicts with another node in the cluster, then the node is not accepted as part of the cluster.
The rest of the cluster continues to handle the traffic.

This operation changes the configuration on all cluster nodes.
As a result, the NLB cluster restarts the convergence process on all nodes to guarantee that configuration changes have been applied on all nodes and that a consistent state is reached.
Any additional operations on the NLB cluster are not initiated until all cluster nodes have completed the convergence process and are back to the converged state.

ps_nlbc_checkstate_remark

## EXAMPLES

### Example 1: Change the handling priority of a given port rule
```
PS C:\>Get-NlbClusterNode -NodeName "Node001" | Get-NlbClusterPortRule | Set-NlbClusterPortRuleNodeHandlingPriority -HandlingPriority 3
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout
--------- -----     -----     ---       --------  ----      --------  -------
All       Enabled   0         65535     Both      Single
```

This command changes the handling priority of the given port rule for the node named Node001 to 3.
This is applicable for port rules with Single mode.

### Example 2: Change the handling priority of a given port rule
```
PS C:\>Set-NlbClusterPortRuleNodeHandlingPriority -HostName "Node002" -Interface "Vlan-3" -IP 255.255.255.255 -Port 80 -HandlingPriority 4
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout
--------- -----     -----     ---       --------  ----      --------  -------
All       Enabled   0         65535     Both      Single
```

This command changes the handling priority of the given port rule for the node named Node001 to 4.
This is applicable for port rules with Single mode.

## PARAMETERS

### -HandlingPriority
Specifies the handling priority for the cluster node.
This is only applicable when the filtering mode of the port rule is Single host.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: HP

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
Parameter Sets: NonPipeline
Aliases: Host, HN, H

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IP
Specifies the IP address for the cluster port rule on which this cmdlet sets the handling priority.

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
Specifies the cluster port rule on which this cmdlet set the handling priority.
This is only applicable when the filtering mode for the port rule is Single host.

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

### -Port
Specifies a port number within the port rule on which this cmdlet sets the node handling priority.
The acceptable values for this parameter are:0 through 65535.

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

[Set-NlbClusterPortRule](./Set-NlbClusterPortRule.md)

[Set-NlbClusterPortRuleNodeWeight](./Set-NlbClusterPortRuleNodeWeight.md)

