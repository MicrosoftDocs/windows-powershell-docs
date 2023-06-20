---
external help file: Failoverv2_Cmdlets.xml
Module Name: FailoverClusters
online version: https://learn.microsoft.com/powershell/module/failoverclusters/start-clusternode?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Start-ClusterNode

## SYNOPSIS
Starts the Cluster service on a node in a failover cluster.

## SYNTAX

```
Start-ClusterNode [[-Name] <StringCollection>] [-Cluster <String>] [-FixQuorum] [-IgnorePersistentState]
 [-InputObject <PSObject>] [-PreventQuorum] [-Wait <Int32>]
```

## DESCRIPTION
The **Start-ClusterNode** cmdlet starts the Cluster service on a node in a failover cluster.
If this is the first node started, then it will wait for other nodes to join.
The cluster will begin to run when a quorum has formed.

This cmdlet with the **FixQuorum** parameter can be used to force quorum, that is, force the start of a cluster node even if quorum has not been achieved.
When quorum is forced on a given node, the copy of the cluster configuration that is on that node will be treated as the authoritative copy and will be replicated to all other nodes.
Therefore, forcing quorum should be considered a last resort, because some cluster configuration changes could be lost.
The ability to force quorum can be especially useful in a multi-site cluster if the primary site, with the majority of nodes, becomes unavailable, and the secondary site, with a minority of nodes, need to be brought into service.
Similarly, the ability to force quorum makes it possible to start a cluster that uses the Node and File Share Majority quorum option when none of the available cluster nodes contains a current copy of the cluster configuration.

Note: This cmdlet cannot be run remotely without Credential Security Service Provider (CredSSP) authentication on the server computer.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Start-ClusterNode -Name node3
Name                                                                      State 
----                                                                      ----- 
node3                                                                   Joining
```

This example starts the Cluster service on the node named node3 on the local cluster.

### EXAMPLE 2
```
PS C:\>Start-ClusterNode -Name node1 -Cluster cluster2
Name                                                                      State 
----                                                                      ----- 
node1                                                                   Joining
```

This example starts the Cluster service on the node named node1 on the cluster named cluster2.

### EXAMPLE 3
```
PS C:\>Start-ClusterNode -FixQuorum
Name                                                                      State 
----                                                                      ----- 
node1                                                                   Joining
```

This example forces the local node and the local cluster to start, even if quorum has not been achieved.
If quorum has not been achieved, then the copy of the cluster configuration that is on the local node will be treated as the authoritative copy and will be replicated to all other nodes.
This cmdlet should be considered a last resort, because some cluster configuration changes could be lost.

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

### -FixQuorum
Forces quorum on this node, which means that the copy of the cluster configuration that is on this node will be treated as the authoritative copy and will be replicated to all other nodes.
Forcing quorum should be considered a last resort.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: fq

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnorePersistentState
Starts the cluster node without bringing resources online on the node.

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
Specifies the cluster node to start.

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
Specifies the name of the cluster node to start.

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

### -PreventQuorum
Starts the node, but prevents it from achieving quorum and forming the cluster, to prevent a split situation with two competing instances of the cluster running.

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

### -Wait
Specifies the time in seconds to wait for the cmdlet.
If the **Wait** parameter is not specified, then the cmdlet waits for completion.
If `-Wait 0` is specified, then the call is initiated and the cmdlet returns without waiting.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterNode

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterNode

## NOTES

## RELATED LINKS

[Add-ClusterNode](./Add-ClusterNode.md)

[Get-ClusterNode](./Get-ClusterNode.md)

[Remove-ClusterNode](./Remove-ClusterNode.md)

[Resume-ClusterNode](./Resume-ClusterNode.md)

[Stop-ClusterNode](./Stop-ClusterNode.md)

[Suspend-ClusterNode](./Suspend-ClusterNode.md)

