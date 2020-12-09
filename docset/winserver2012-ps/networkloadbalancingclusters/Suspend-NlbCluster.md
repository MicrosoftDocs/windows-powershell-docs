---
external help file: NLB_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: B67E9CB4-15B0-4BB2-8DDC-8946AB42C757
manager: dansimp
---

# Suspend-NlbCluster

## SYNOPSIS
Suspends all nodes of a Network Load Balancing (NLB) cluster.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Suspend-NlbCluster [[-HostName] <String>] [[-InterfaceName] <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Suspend-NlbCluster -InputObject <Cluster>
```

## DESCRIPTION
The **Suspend-NlbCluster** cmdlet suspends all nodes of a Network Load Balancing (NLB) cluster.
A cluster may need to be suspended to override any remote control cmdlets, or non-Windows PowerShell® operations, that are issued and for maintenance work.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Suspend-NlbCluster
Name                IPAddress           SubnetMask          Mode 
----                ---------           ----------          ---- 
cluster1            3.53.100.100        255.0.0.0           UNICAST
```

This example suspends all cluster nodes on the local cluster.

## PARAMETERS

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
Specifies the cluster to suspend.

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

Required: False
Position: 2
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

[Set-NlbCluster](./Set-NlbCluster.md)

[Start-NlbCluster](./Start-NlbCluster.md)

[Stop-NlbCluster](./Stop-NlbCluster.md)

[Suspend-NlbClusterNode](./Suspend-NlbClusterNode.md)

