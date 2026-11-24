---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 10/21/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/resume-clusternode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-ClusterNode
---

# Resume-ClusterNode

## SYNOPSIS
Resumes a node from the paused state or brings back drained workloads to the node or both.

## SYNTAX

```
Resume-ClusterNode [[-Name] <StringCollection>] [[-Failback] <ResumeClusterNodeFailbackType>]
 [-InputObject <PSObject>] [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Resume-ClusterNode` cmdlet resumes activity on a failover cluster node after it has been
suspended, or paused, or brings back drained workloads to the node, or both. When a node is resumed,
clustered roles that were drained from the node are returned to it, and clustered roles or resources
that are currently offline can be brought online on that node.

## EXAMPLES

### Example 1

```powershell
Resume-ClusterNode node1
```

This example resumes node1 on the local cluster.

### Example 2

```powershell
Resume-ClusterNode node2 -Cluster mycluster
```

This example resumes node2 on the cluster called `mycluster`.

### Example 3

```powershell
Get-ClusterNode | Resume-ClusterNode
```

This example resumes all cluster nodes that are suspended, or paused, on the local cluster.

### Example 4

```powershell
Get-ClusterNode | Resume-ClusterNode -Failback Immediate
```

This example resumes all cluster nodes that are suspended, or paused, on the local cluster and
immediately brings back the workloads drained from the nodes.

## PARAMETERS

### -Cluster

Specifies the name of the cluster on which to run this cmdlet. If the input for this parameter is
`.` or it is omitted, then the cmdlet runs on the local cluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Failback

Sets the policy to bring back drained workloads to the node. The acceptable values for this
parameter are:

- `NoFailBack` - Don't failback at all.
- `Immediate` - Failback immediately.
- `Policy` - Failback only during specific hours.

```yaml
Type: ResumeClusterNodeFailbackType
Parameter Sets: (All)
Aliases:
Accepted values: NoFailback, Immediate, Policy

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Specifies the group, node, resource, or service for which or cluster on which to run the cmdlet.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Specifies the name of the group, node, resource, or service for which or cluster on which to run the
cmdlet.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterNode

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterNode

## NOTES

## RELATED LINKS

[Add-ClusterNode](./Add-ClusterNode.md)

[Clear-ClusterNode](./Clear-ClusterNode.md)

[Get-ClusterNode](./Get-ClusterNode.md)

[Remove-ClusterNode](./Remove-ClusterNode.md)

[Start-ClusterNode](./Start-ClusterNode.md)

[Stop-ClusterNode](./Stop-ClusterNode.md)

[Suspend-ClusterNode](./Suspend-ClusterNode.md)
