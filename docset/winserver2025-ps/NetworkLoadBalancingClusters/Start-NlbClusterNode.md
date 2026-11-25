---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/start-nlbclusternode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-NlbClusterNode
---

# Start-NlbClusterNode

## SYNOPSIS
Starts a NLB cluster node.

## SYNTAX

### NonPipeline (Default)
```
Start-NlbClusterNode [[-HostName] <String>] [-InterfaceName <String>] [<CommonParameters>]
```

### Pipeline
```
Start-NlbClusterNode -InputObject <Node[]> [<CommonParameters>]
```

## DESCRIPTION
The **Start-NlbClusterNode** cmdlet starts a node in a Network Load Balancing (NLB) cluster.
Once the node is started, NLB includes that node in load balancing network traffic.

## EXAMPLES

### Example 1: Start a cluster node on the local cluster
```
PS C:\>Start-NlbClusterNode -InputObject "Node2"
Name                State               Interface           HostID
----                -----               ---------           ------
Node2               Converged           vlan-3              2
```

This example starts cluster node named Node2 on the local cluster.

## PARAMETERS

### -HostName
Specifies the name of the cluster host against which this cmdlet is run.
If this parameter is omitted or a value of `.` is entered, then the local cluster is assumed.

```yaml
Type: String
Parameter Sets: NonPipeline
Aliases: Host, HN, H

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies an array of cluster nodes that this cmdlet starts.

```yaml
Type: Node[]
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Node

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Node

## NOTES

## RELATED LINKS

[Add-NlbClusterNode](./Add-NlbClusterNode.md)

[Get-NlbClusterNode](./Get-NlbClusterNode.md)

[Remove-NlbClusterNode](./Remove-NlbClusterNode.md)

[Resume-NlbClusterNode](./Resume-NlbClusterNode.md)

[Set-NlbClusterNode](./Set-NlbClusterNode.md)

[Stop-NlbClusterNode](./Stop-NlbClusterNode.md)

[Suspend-NlbClusterNode](./Suspend-NlbClusterNode.md)

