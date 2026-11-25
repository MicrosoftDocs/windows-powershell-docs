---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/start-nlbcluster?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-NlbCluster
---

# Start-NlbCluster

## SYNOPSIS
Starts all nodes in a NLB cluster.

## SYNTAX

### NonPipeline (Default)
```
Start-NlbCluster [[-HostName] <String>] [[-InterfaceName] <String>] [<CommonParameters>]
```

### Pipeline
```
Start-NlbCluster -InputObject <Cluster[]> [<CommonParameters>]
```

## DESCRIPTION
The **Start-NlbCluster** cmdlet starts all nodes in a Network Load Balancing (NLB) cluster.
Once the nodes are started, NLB includes all cluster nodes in load balancing network traffic.

## EXAMPLES

### Example 1: Start all cluster nodes on the local cluster
```
PS C:\>Start-NlbCluster
Name                IPAddress           SubnetMask          Mode
----                ---------           ----------          ----
cluster1            3.53.100.100        255.0.0.0           UNICAST
```

This command starts all of the cluster nodes on the local cluster.

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
Specifies an array of clusters that this cmdlet starts.

```yaml
Type: Cluster[]
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

[Stop-NlbCluster](./Stop-NlbCluster.md)

[Suspend-NlbCluster](./Suspend-NlbCluster.md)

