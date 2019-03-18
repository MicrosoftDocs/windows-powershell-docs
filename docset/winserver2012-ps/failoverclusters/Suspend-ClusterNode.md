---
external help file: Failoverv2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 6BE0D49E-A27C-4640-AE0D-0B1E47B2999E
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Suspend-ClusterNode

## SYNOPSIS
Suspends activity on a failover cluster node, that is, pauses the node.

## SYNTAX

```
Suspend-ClusterNode [[-Name] <StringCollection>] [[-TargetNode] <String>] [-Cluster <String>] [-Drain]
 [-ForceEvacuation] [-InputObject <PSObject>] [-Wait]
```

## DESCRIPTION
The **Suspend-ClusterNode** cmdlet suspends activity on a failover cluster node, that is, pauses the node.
If you use the **Drain** parameter, clustered roles currently running on the node will be drained before the node is paused.

Pausing (suspending) a node is usually done when applying software updates to the node.
If you need to perform extensive diagnosis or maintenance on a cluster node, it might be more workable to stop (not pause) the Cluster service on that node.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Suspend-ClusterNode node1
Name                                                                      State 
----                                                                      ----- 
node1                                                                    Paused
```

This example pauses the node named node1 on the local cluster.

### EXAMPLE 2
```
PS C:\>Suspend-ClusterNode node2 -Cluster cluster2
Name                                                                      State 
----                                                                      ----- 
node2                                                                    Paused
```

This example pauses the node named node2 on the cluster named cluster2.

### EXAMPLE 3
```
PS C:\>Suspend-ClusterNode -Name node1 -Target node2 -Drain
Name                                                                      State 
----                                                                      ----- 
node1                                                                    Paused
```

This example pauses the node named node1 and moves the workloads from it to the node named node2.

### EXAMPLE 4
```
PS C:\>Suspend-ClusterNode node1 -Drain -WhatIf
What if: Performing operation "Suspend-ClusterNode" on Target "node1".
```

This example provides a preview of the operation that will be performed on the node named node1.

## PARAMETERS

### -Cluster
Specifies the name of the cluster on which to run this cmdlet.
If the input for this parameter is `.` or it is omitted, then the cmdlet runs on the local cluster.

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

### -Drain
Specifies that all of the workloads are gracefully moved to other nodes while maintaining the highest levels of availability and using the best placement logic.

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

### -ForceEvacuation
Specifies that workloads are moved from a node even in the case of an error.

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
Specifies the cluster node to suspend (with or without draining), or the cluster on which to run the cmdlet.

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
Specifies the name of the cluster node to suspend (with or without draining).

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
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
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait
Specifies the time in seconds to wait for the cmdlet.
If the **Wait** parameter is not specified, then the cmdlet waits for completion.
If `-Wait 0` is specified, then the call is initiated and the cmdlet returns without waiting.

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

