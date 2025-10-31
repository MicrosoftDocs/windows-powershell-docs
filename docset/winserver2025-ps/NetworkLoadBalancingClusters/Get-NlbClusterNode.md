---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/get-nlbclusternode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NlbClusterNode
---

# Get-NlbClusterNode

## SYNOPSIS
Gets information about a node object or the NLB cluster object that is queried by the caller.

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
The **Get-NlbClusterNode** cmdlet gets information about a node in the Network Load Balancing (NLB) cluster.
The information includes the properties, or attributes, that define the node and its status.

## EXAMPLES

### Example 1: List nodes that belong to the local cluster
```
PS C:\>Get-NlbClusterNode
Name                State               Interface           HostID
----                -----               ---------           ------
node1               Converged(default)  vlan-3              1
node2               Converged           vlan-3              2
```

This command lists nodes that are part of the local cluster.
It also shows the state of the nodes and the interface to which NLB is bound on each node.

### Example 2: Get details about a cluster node
```
PS C:\>Get-NlbClusterNode -NodeName "Node01" | Format-List *
Cluster                   : mycluster
Name                      : Node01
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

This command gets details about cluster node named Node01.

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
Specifies an array of clusters for which this cmdlet enumerates the nodes.

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
Specifies the cluster node name that this cmdlet gets.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

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

