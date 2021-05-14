---
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/networkloadbalancingclusters/get-nlbclusternode?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NlbClusterNode
---

# Get-NlbClusterNode

## SYNOPSIS
Retrieves information about a node object or the Network Load Balancing (NLB) cluster object that is queried by the caller.

## SYNTAX

### NonPipeline (Default)
```
Get-NlbClusterNode [-HostName <String>] [-InterfaceName <String>] [[-NodeName] <String>] [<CommonParameters>]
```

### Pipeline
```
Get-NlbClusterNode -InputObject <Cluster[]> [-HostName <String>] [[-NodeName] <String>] [<CommonParameters>]
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
Aliases: Host, HN, H

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster for which the nodes are enumerated.

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
Aliases: Name, NN

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

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

