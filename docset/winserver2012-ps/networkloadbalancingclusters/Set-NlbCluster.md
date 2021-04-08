---
author: Kateyanne
external help file: NLB_Cmdlets.xml
manager: dansimp
Module Name: NetworkLoadBalancingClusters
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/networkloadbalancingclusters/set-nlbcluster?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NlbCluster

## SYNOPSIS
Edits the configuration of a Network Load Balancing (NLB) cluster.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NlbCluster [[-HostName] <String>] [-InterfaceName] <String> [-ClusterPrimaryIP <IPAddress>]
 [-Name <String>] [-OperationMode <Nullable>]
```

### UNNAMED_PARAMETER_SET_2
```
Set-NlbCluster [-ClusterPrimaryIP <IPAddress>] [-Name <String>] [-OperationMode <Nullable>]
 -InputObject <Cluster>
```

## DESCRIPTION
The **Set-NlbCluster** cmdlet edits the configuration of a Network Load Balancing (NLB) cluster.
The configuration changes you can make include the cluster operation mode (MULTICAST or UNICAST), the cluster name, and the cluster primary IP address.

This operation changes the configuration on all cluster nodes.
As a result, the NLB cluster will have to restart the convergence process on all nodes to guarantee that configuration changes have been applied on all nodes and that a consistent state is reached.
Any additional operations on the NLB cluster should not be initiated until all cluster nodes have completed the convergence process and are back to the converged state.

ps_nlbc_checkstate_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NlbCluster | Set-NlbCluster -Name newcluster
Name                IPAddress           SubnetMask          Mode 
----                ---------           ----------          ---- 
newcluster          fe80::b349:6945:... ::                  UNICAST
```

This example changes the cluster name to newcluster.

### EXAMPLE 2
```
PS C:\>Get-NlbCluster | Set-NlbCluster -OperationMode MULTICAST
Name                IPAddress           SubnetMask          Mode 
----                ---------           ----------          ---- 
newcluster          fe80::b349:6945:... ::                  MULTICAST
```

This example changes the cluster operation mode to MULTICAST.

### EXAMPLE 3
```
PS C:\>Get-NlbCluster | Set-NlbCluster -ClusterPrimaryIP 2.53.0.120
Name                IPAddress           SubnetMask          Mode 
----                ---------           ----------          ---- 
newcluster          2.53.0.120          255.0.0.0           MULTICAST
```

This example changes the cluster primary IP address to one of the other cluster virtual IP addresses on the cluster.

## PARAMETERS

### -ClusterPrimaryIP
Specifies the IP address to use as the cluster primary IP address.
The IP address must be one of the existing virtual IP addresses on the cluster.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: pip, primaryip

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostName
Specifies the name of the cluster host against which this cmdlet is run.
If this parameter is omitted or a value of `.` is entered, then the local cluster is assumed.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: hn

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster to set.

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

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the new name of the cluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases: clustername

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OperationMode
Specifies the new operation mode for the cluster.
The acceptable values for this parameter are:IGMPMULTICAST, MULTICAST, or UNICAST.

```yaml
Type: Nullable
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Cluster

## NOTES

## RELATED LINKS

[Get-NlbCluster](./Get-NlbCluster.md)

[New-NlbCluster](./New-NlbCluster.md)

[Remove-NlbCluster](./Remove-NlbCluster.md)

[Resume-NlbCluster](./Resume-NlbCluster.md)

[Start-NlbCluster](./Start-NlbCluster.md)

[Stop-NlbCluster](./Stop-NlbCluster.md)

[Suspend-NlbCluster](./Suspend-NlbCluster.md)

