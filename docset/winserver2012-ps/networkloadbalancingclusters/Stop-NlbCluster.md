---
author: Kateyanne
external help file: NLB_Cmdlets.xml
manager: dansimp
Module Name: NetworkLoadBalancingClusters
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/networkloadbalancingclusters/stop-nlbcluster?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Stop-NlbCluster

## SYNOPSIS
Stops all nodes of a Network Load Balancing (NLB) cluster.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Stop-NlbCluster [[-HostName] <String>] [[-InterfaceName] <String>] [-Drain] [-Timeout <Nullable>]
```

### UNNAMED_PARAMETER_SET_2
```
Stop-NlbCluster [-Drain] [-Timeout <Nullable>] -InputObject <Cluster>
```

## DESCRIPTION
The **Stop-NlbCluster** cmdlet stops all nodes in a Network Load Balancing (NLB) cluster.
The cmdlet will stop the NLB service on the host and all existing connections will be lost.
To avoid interrupting active connections, use the **Drain** parameter which allows the host to continue servicing active connections, but disables all new traffic to that host.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Stop-NlbCluster
Name                IPAddress           SubnetMask          Mode 
----                ---------           ----------          ---- 
cluster1            3.53.100.100        255.0.0.0           UNICAST
```

This example stops all cluster nodes on the local cluster.

## PARAMETERS

### -Drain
Drains existing traffic before stopping the cluster.
If this parameter is omitted, then the existing traffic will be dropped.

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
Specifies the cluster to stop.

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

### -Timeout
Specifies the number of minutes to wait for the drain operation before stopping the cluster.
After the time expires, the existing connections will be dropped.

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

[Set-NlbCluster](./Set-NlbCluster.md)

[Start-NlbCluster](./Start-NlbCluster.md)

[Suspend-NlbCluster](./Suspend-NlbCluster.md)

