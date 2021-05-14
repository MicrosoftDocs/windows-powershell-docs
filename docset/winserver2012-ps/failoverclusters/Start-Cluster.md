---
external help file: Failoverv2_Cmdlets.xml
Module Name: FailoverClusters
online version: https://docs.microsoft.com/powershell/module/failoverclusters/start-cluster?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Start-Cluster

## SYNOPSIS
Starts the Cluster service on all nodes of the cluster on which it is not yet started.

## SYNTAX

```
Start-Cluster [[-Name] <String>] [-IgnorePersistentState] [-Wait <Int32>]
```

## DESCRIPTION
The **Start-Cluster** cmdlet starts the Cluster service on all nodes of the cluster on which it is not yet started.
A node can function as part of the cluster only when the Cluster service is running on that node.

Note: This cmdlet cannot be run remotely without Credential Security Service Provider (CredSSP) authentication on the server computer.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Start-Cluster
Name 
---- 
mycluster
```

This example starts all cluster nodes on the local cluster.

### EXAMPLE 2
```
PS C:\>Start-Cluster -Name node2
Name 
---- 
mycluster
```

This example starts all cluster nodes on the cluster of which the node named node2 is a part.
A node name is required if all cluster nodes are stopped.
If the cluster is already running, then the cluster name, assuming the cluster name resource is online, can be used instead of the node name.

## PARAMETERS

### -IgnorePersistentState
Starts the nodes in the cluster without bringing resources online on the nodes.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: IPS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the cluster to start.

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
Specifies the time in seconds to wait for the cmdlet.
If this parameter is not specified, then the cmdlet will not return until quorum is achieved.
If the value of `0` is specified, the cmdlet will attempt to start the Cluster service on all nodes and then return without waiting.

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

### None

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## NOTES

## RELATED LINKS

[Get-Cluster](./Get-Cluster.md)

[Get-ClusterNode](./Get-ClusterNode.md)

[New-Cluster](./New-Cluster.md)

[Remove-Cluster](./Remove-Cluster.md)

[Stop-Cluster](./Stop-Cluster.md)

[Test-Cluster](./Test-Cluster.md)

