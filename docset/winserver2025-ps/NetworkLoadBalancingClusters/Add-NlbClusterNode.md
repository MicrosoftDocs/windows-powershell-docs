---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/add-nlbclusternode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-NlbClusterNode
---

# Add-NlbClusterNode

## SYNOPSIS
Adds a new node to the Network Load Balancing (NLB) cluster.

## SYNTAX

### NonPipeline (Default)
```
Add-NlbClusterNode [-HostName <String>] -InterfaceName <String> [-NewNodeName] <String>
 [-NewNodeInterface] <String> [-Force] [<CommonParameters>]
```

### Pipeline
```
Add-NlbClusterNode -InputObject <Cluster[]> [-NewNodeName] <String> [-NewNodeInterface] <String> [-Force]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-NlbClusterNode** cmdlet adds a new node to the Network Load Balancing (NLB) cluster.
Once the new node settings are circulated through all of the NLB cluster nodes, the new cluster node will be in a running state in the cluster.

This cmdlet changes the configuration on all cluster nodes.
As a result, the NLB cluster will have to restart the convergence process on all nodes to guarantee that configuration changes have been applied on all nodes and that a consistent state is reached.
Any additional operations on the NLB cluster should not be initiated until all cluster nodes have completed the convergence process and are back to the converged state.

ps_nlbc_checkstate_remark

## EXAMPLES

### Example 1: Add a new node to an NLB cluster
```
PS C:\>Get-NlbCluster "Node001" | Add-NlbClusterNode -NewNodeName "Node002" -NewNodeInterface "Vlan-3"
Name                State               Interface           HostID
----                -----               ---------           ------
node2               Converged           vlan-3              2
```

This command adds the host named Node002 to the cluster on the node named Node001 using the interface named Vlan-3.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: F

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

### -InputObject
Specifies an array of clusters to which the node is added.

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

### -NewNodeInterface
Specifies the interface name on the new cluster node.

```yaml
Type: String
Parameter Sets: (All)
Aliases: NewInterface, NI

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewNodeName
Specifies the name of the new cluster node.

```yaml
Type: String
Parameter Sets: (All)
Aliases: NewNode, NN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Node

## NOTES

## RELATED LINKS

[Get-NlbClusterNode](./Get-NlbClusterNode.md)

[Remove-NlbClusterNode](./Remove-NlbClusterNode.md)

[Resume-NlbClusterNode](./Resume-NlbClusterNode.md)

[Set-NlbClusterNode](./Set-NlbClusterNode.md)

[Stop-NlbClusterNode](./Stop-NlbClusterNode.md)

[Suspend-NlbClusterNode](./Suspend-NlbClusterNode.md)

