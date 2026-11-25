---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/23/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/suspend-clusternode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-ClusterNode
---

# Suspend-ClusterNode

## SYNOPSIS
Suspends activity on a failover cluster node, that is, pauses the node.

## SYNTAX

```
Suspend-ClusterNode [[-Name] <StringCollection>] [-Drain] [-ForceDrain] [-Wait]
 [[-TargetNode] <String>] [-InputObject <PSObject>] [-Cluster <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The `Suspend-ClusterNode` cmdlet suspends activity on a failover cluster node, that is, pauses the
node. If you use the **Drain** parameter, clustered roles currently running on the node will be
drained before the node is paused.

Pausing, or suspending, a node is usually done when applying software updates to the node. If you
need to perform extensive diagnosis or maintenance on a cluster node, it might be more workable to
stop, not pause, the Cluster service on that node.

## EXAMPLES

### Example 1: Pause a node of the local cluster

```powershell
Suspend-ClusterNode -Name "node1"
```

This example pauses the node named `node1` on the local cluster.

### Example 2: Pause a node of a cluster

```powershell
Suspend-ClusterNode "node2" -Cluster "cluster2"
```

This example pauses the node named `node2` on the cluster named `cluster2`.

### Example 3: Pause a node and move its workloads

```powershell
Suspend-ClusterNode -Name "node1" -Target "node2" -Drain
```

This example pauses the node named `node1` and moves the workloads from it to the node named
`node2`.

### Example 4: Preview a pause operation

```powershell
Suspend-ClusterNode node1 -Drain -WhatIf
```

This example provides a preview of the operation that will be performed on the node named `node1`.

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

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Drain

Specifies that all of the workloads are gracefully moved to other nodes while maintaining the
highest levels of availability and using the best placement logic.

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

### -ForceDrain

The -ForceDrain switch, used in conjunction with the -Drain switch, allows all the workloads to be
safely moved to other nodes, while maintaining the highest levels of availability and using the best
placement logic.

If some or all of the workloads can't be moved safely, any workload that failed will be stopped and
moved to another node as a failed role. Thereafter, the node will be forced to pause.

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

### -InputObject

Specifies the cluster node to suspend, with or without draining, or the cluster on which to run the
cmdlet.

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

Specifies the name of the cluster node to suspend, with or without draining.

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

### -TargetNode

Specifies a node to which to drain the workloads.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait

Specifies the time in seconds to wait for the cmdlet. If the **Wait** parameter isn't specified,
then the call is initiated and the cmdlet returns without waiting. If specified with no value, then
the cmdlet waits for completion. If `-Wait 0` is specified, then the call is initiated and the
cmdlet returns without waiting.

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

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

### Microsoft.FailoverClusters.PowerShell.ClusterNode

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterNode

## NOTES

## RELATED LINKS

[Add-ClusterNode](./Add-ClusterNode.md)

[Get-ClusterNode](./Get-ClusterNode.md)

[Remove-ClusterNode](./Remove-ClusterNode.md)

[Resume-ClusterNode](./Resume-ClusterNode.md)

[Start-ClusterNode](./Start-ClusterNode.md)

[Stop-ClusterNode](./Stop-ClusterNode.md)
