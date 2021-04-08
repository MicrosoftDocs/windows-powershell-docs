---
author: Kateyanne
external help file: NLB_Cmdlets.xml
manager: dansimp
Module Name: NetworkLoadBalancingClusters
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/networkloadbalancingclusters/add-nlbclusternode?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-NlbClusterNode

## SYNOPSIS
Adds a new node to the Network Load Balancing (NLB) cluster.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-NlbClusterNode [-NewNodeName] <String> [-NewNodeInterface] <String> [-Force] [-HostName <String>]
 -InterfaceName <String>
```

### UNNAMED_PARAMETER_SET_2
```
Add-NlbClusterNode [-NewNodeName] <String> [-NewNodeInterface] <String> [-Force] -InputObject <Cluster>
```

## DESCRIPTION
The **Add-NlbClusterNode** cmdlet adds a new node to the Network Load Balancing (NLB) cluster.
Once the new node settings are circulated through all of the NLB cluster nodes, the new cluster node will be in a running state in the cluster.

This cmdlet changes the configuration on all cluster nodes.
As a result, the NLB cluster will have to restart the convergence process on all nodes to guarantee that configuration changes have been applied on all nodes and that a consistent state is reached.
Any additional operations on the NLB cluster should not be initiated until all cluster nodes have completed the convergence process and are back to the converged state.

ps_nlbc_checkstate_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NlbCluster node1 | Add-NlbClusterNode -NewNodeName node2 -NewNodeInterface vlan-3
Name                State               Interface           HostID 
----                -----               ---------           ------ 
node2               Converged           vlan-3              2
```

This example adds the host named node2 to the cluster on the node named node1.

## PARAMETERS

### -Force
Runs the cmdlet without prompting for confirmation.
By default the cmdlet asks for confirmation from the user before proceeding.

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

### -InputObject
Specifies the cluster to which the node is added.

```yaml
Type: Cluster
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

### -NewNodeInterface
Specifies the interface name on the new cluster node.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ni

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewNodeName
Specifies the name of the new cluster node.

```yaml
Type: String
Parameter Sets: (All)
Aliases: nn

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

