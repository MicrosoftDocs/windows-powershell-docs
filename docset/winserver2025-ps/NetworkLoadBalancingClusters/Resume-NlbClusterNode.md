---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/resume-nlbclusternode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-NlbClusterNode
---

# Resume-NlbClusterNode

## SYNOPSIS
Resumes a node in a NLB cluster.

## SYNTAX

### NonPipeline (Default)
```
Resume-NlbClusterNode [[-HostName] <String>] [[-InterfaceName] <String>] [<CommonParameters>]
```

### Pipeline
```
Resume-NlbClusterNode -InputObject <Node[]> [<CommonParameters>]
```

## DESCRIPTION
The **Resume-NlbClusterNode** cmdlet resumes the node in a Network Load Balancing (NLB) cluster that was suspended.
To override any remote control cmdlets that are issued, a node may need to be suspended and resumed.

## EXAMPLES

### Example 1: Resume the local cluster node
```
PS C:\>Resume-NlbClusterNode
Name                State               Interface           HostID
----                -----               ---------           ------
node2               Stopped             vlan-3              2
```

This command resumes the local cluster node.
The node is in the Stopped state and needs to be started after coming back from the Suspended state.

### Example 2: Resume the specified cluster node on the local cluster
```
PS C:\>Resume-NlbClusterNode -InputObject "Node003"
Name                State               Interface           HostID
----                -----               ---------           ------
Node003               Stopped             vlan-3              2
```

This command resumes the cluster node named Node003 on the local cluster.
The node is in the Stopped state and needs to be started after coming back from the Suspended state.

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
Specifies an array of cluster nodes to resume.

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
Position: 1
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

[Set-NlbClusterNode](./Set-NlbClusterNode.md)

[Start-NlbClusterNode](./Start-NlbClusterNode.md)

[Stop-NlbClusterNode](./Stop-NlbClusterNode.md)

[Suspend-NlbClusterNode](./Suspend-NlbClusterNode.md)

