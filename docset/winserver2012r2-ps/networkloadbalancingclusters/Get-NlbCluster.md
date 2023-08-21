---
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/get-nlbcluster?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NlbCluster
---

# Get-NlbCluster

## SYNOPSIS
Retrieves information about the Network Load Balancing (NLB) cluster object that is queried by the caller.

## SYNTAX

```
Get-NlbCluster [[-HostName] <String>] [[-InterfaceName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NlbCluster** cmdlet retrieves information about the Network Load Balancing (NLB) cluster.
The information includes the properties, or attributes, that define the cluster and its status.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NlbCluster
Name                IPAddress           SubnetMask          Mode 
----                ---------           ----------          ---- 
cluster1            3.53.100.100        255.0.0.0           UNICAST
```

This example gets the cluster object for the local NLB cluster, that is, the cluster that this node is a part.

### EXAMPLE 2
```
PS C:\>Get-NlbCluster -HostName node1
Name                IPAddress           SubnetMask          Mode 
----                ---------           ----------          ---- 
cluster2            4.53.100.100        255.0.0.0           UNICAST
```

This example gets the cluster object for the NLB cluster that node named node1 is a part.

### EXAMPLE 3
```
PS C:\>Get-NlbCluster -HostName node1 -InterfaceName vlan-2
Name                IPAddress           SubnetMask          Mode 
----                ---------           ----------          ---- 
cluster2            4.53.100.100        255.0.0.0           UNICAST
```

This example gets the cluster object for the NLB cluster that node named node1 (with the interface named vlan-2) is a part.

## PARAMETERS

### -HostName
Specifies the name of the cluster host against which this cmdlet is run.
If this parameter is omitted or a value of `.` is entered, then the local cluster is assumed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Host, HN, H

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterfaceName
Specifies the interface to which NLB is bound.
This is the interface of the cluster against which this cmdlet is run.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Interface, IN, I

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Cluster

## NOTES

## RELATED LINKS

[New-NlbCluster](./New-NlbCluster.md)

[Remove-NlbCluster](./Remove-NlbCluster.md)

[Resume-NlbCluster](./Resume-NlbCluster.md)

[Set-NlbCluster](./Set-NlbCluster.md)

[Start-NlbCluster](./Start-NlbCluster.md)

[Stop-NlbCluster](./Stop-NlbCluster.md)

[Suspend-NlbCluster](./Suspend-NlbCluster.md)

