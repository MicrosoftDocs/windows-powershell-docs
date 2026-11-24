---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/add-nlbclusterportrule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-NlbClusterPortRule
---

# Add-NlbClusterPortRule

## SYNOPSIS
Adds a new port rule to a Network Load Balancing (NLB) cluster.

## SYNTAX

### NonPipeline (Default)
```
Add-NlbClusterPortRule [-HostName <String>] -InterfaceName <String> [-IP <IPAddress>]
 [-Protocol <PortRuleProtocol>] [-StartPort] <Int32> [-EndPort] <Int32> [-Mode <PortRuleFilteringMode>]
 [-Affinity <PortRuleAffinity>] [-Timeout <UInt32>] [<CommonParameters>]
```

### Pipeline
```
Add-NlbClusterPortRule -InputObject <Cluster[]> [-IP <IPAddress>] [-Protocol <PortRuleProtocol>]
 [-StartPort] <Int32> [-EndPort] <Int32> [-Mode <PortRuleFilteringMode>] [-Affinity <PortRuleAffinity>]
 [-Timeout <UInt32>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-NlbClusterPortRule** cmdlet adds a new port rule to a Network Load Balancing (NLB) cluster.
Port rules control how an NLB cluster functions.
To maximize the control of various types of TCP/IP traffic, you can set up port rules to control how each port's cluster-network traffic is handled.
The method by which a port's network traffic is handled is called its filtering mode.
There are three possible filtering modes: Multiple hosts, Single host, and Disabled.
A filtering mode can also apply to a numerical range of ports.
You do this by defining a port rule with a set of configuration parameters that define the filtering mode.
In addition, you can select one of three options for client affinity: None, Single, or Network.
Single and Network are used to ensure that all network traffic from a particular client is directed to the same cluster host.
To allow NLB to properly handle IP fragments, you should avoid using None when you select UDP or Both for your protocol setting.

This cmdlet changes the configuration on all cluster nodes.
As a result, the NLB cluster will have to restart the convergence process on all nodes to guarantee that configuration changes have been applied on all nodes and that a consistent state is reached.
Any additional operations on the NLB cluster should not be initiated until all cluster nodes have completed the convergence process and are back to the converged state.

ps_nlbc_checkstate_remark

## EXAMPLES

### Example 1: Add a new port rule to the local cluster
```
PS C:\>Get-NlbCluster | Add-NlbClusterPortRule -StartPort 443 -EndPort 443
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout
--------- -----     -----     ---       --------  ----      --------  -------
All       Enabled   443       443       Both      Multiple  Single    0
```

This command adds a new port rule to the local cluster.
The new port rule covers port 443 only, and uses the default settings for the rest of the port rule parameters.

### Example 2: Add a new port rule to the local cluster with no affinity
```
PS C:\>Get-NlbCluster | Add-NlbClusterPortRule -StartPort 80 -EndPort 80 -Affinity None
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout
--------- -----     -----     ---       --------  ----      --------  -------
All       Enabled   80        80        Both      Multiple  None      0
```

This command adds a new port rule to the local cluster.
The new port rule covers port 80 only and has no affinity, and uses the default settings for the rest of the port rule parameters.

## PARAMETERS

### -Affinity
Specifies the type of affinity for the new port rule.
The acceptable values for this parameter are:

- Network
- None
- Single

```yaml
Type: PortRuleAffinity
Parameter Sets: (All)
Aliases: A
Accepted values: Single, None, Network

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndPort
Specifies the end port for the new port rule.
The acceptable values for this parameter are: 0 through 65535.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: E

Required: True
Position: 1
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
Specifies the IP address for the new cluster port rule.

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

### -InputObject
Specifies the cluster to which the port rule is added.

```yaml
Type: Cluster[]
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

### -Mode
Specifies the filtering mode for the new cluster port rule.
The acceptable values for this parameter are:

- Disabled
- Multiple
- Single

```yaml
Type: PortRuleFilteringMode
Parameter Sets: (All)
Aliases: M
Accepted values: Multiple, Single, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol
Specifies the protocol for the new port rule.
The acceptable values for this parameter are:

- Both
- TCP
- UDP

```yaml
Type: PortRuleProtocol
Parameter Sets: (All)
Aliases: PTCL
Accepted values: Both, Tcp, Udp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartPort
Specifies the start port for the new port rule.
The acceptable values for this parameter are: 0 through 65535.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: S

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Timeout
Specifies the timeout in minutes for the new cluster port rule.
The acceptable values for this parameter are: 0 through 240.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: T

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.PortRule

## NOTES

## RELATED LINKS

[Disable-NlbClusterPortRule](./Disable-NlbClusterPortRule.md)

[Enable-NlbClusterPortRule](./Enable-NlbClusterPortRule.md)

[Get-NlbClusterPortRule](./Get-NlbClusterPortRule.md)

[Remove-NlbClusterPortRule](./Remove-NlbClusterPortRule.md)

[Set-NlbClusterPortRule](./Set-NlbClusterPortRule.md)

