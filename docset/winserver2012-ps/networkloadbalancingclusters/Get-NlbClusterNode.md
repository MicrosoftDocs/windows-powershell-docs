---
external help file: NLB_Cmdlets.xml
Module Name: NetworkLoadBalancingClusters
online version: https://docs.microsoft.com/powershell/module/networkloadbalancingclusters/get-nlbclusternode?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NlbClusterNode

## SYNOPSIS
Retrieves information about a node object or the Network Load Balancing (NLB) cluster object that is queried by the caller.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-NlbClusterNode [[-NodeName] <String>] [-HostName <String>] [-InterfaceName <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-NlbClusterNode [[-NodeName] <String>] [-HostName <String>] -InputObject <Cluster>
```

## DESCRIPTION
The **Get-NlbClusterNode** cmdlet retrieves information about a node in the Network Load Balancing (NLB) cluster.
The information includes the properties, or attributes, that define the node and its status.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NlbClusterNode
Name                State               Interface           HostID 
----                -----               ---------           ------ 
node1               Converged(default)  vlan-3              1 
node2               Converged           vlan-3              2
```

This example lists nodes that are part of the local cluster.
It also shows the state of the nodes and the interface to which NLB is bound on each node.

### EXAMPLE 2
```
PS C:\>Get-NlbClusterNode -NodeName node1 | Format-List *
Cluster                   : mycluster 
Name                      : node1 
InterfaceName             : vlan-3 
Host                      :  
State                     : Converged 
HostPriority              : 2 
AdapterGuid               : {} 
InitialHostState          : Started 
PersistSuspendOnReboot    : True 
MaskSourceMac             : True 
FilterIcmp                : 0 
GreDescriptorTimeout      : 10
```

This example gets details about cluster node named node1.

## PARAMETERS

### -HostName
Specifies the name of the cluster host against which this cmdlet is run.
If this parameter is omitted or a value of `.` is entered, then the local cluster is assumed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: hn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster for which the nodes are enumerated.

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

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeName
Specifies the cluster node name to retrieve.

```yaml
Type: String
Parameter Sets: (All)
Aliases: nn

Required: False
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

[Format-List](https://go.microsoft.com/fwlink/?LinkID=113302)

[Add-NlbClusterNode](./Add-NlbClusterNode.md)

[Remove-NlbClusterNode](./Remove-NlbClusterNode.md)

[Resume-NlbClusterNode](./Resume-NlbClusterNode.md)

[Set-NlbClusterNode](./Set-NlbClusterNode.md)

[Stop-NlbClusterNode](./Stop-NlbClusterNode.md)

[Suspend-NlbClusterNode](./Suspend-NlbClusterNode.md)

