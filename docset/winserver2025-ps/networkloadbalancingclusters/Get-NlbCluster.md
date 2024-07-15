---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/get-nlbcluster?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NlbCluster
---

# Get-NlbCluster

## SYNOPSIS
Gets information about the NLB cluster object that is queried by the caller.

## SYNTAX

```
Get-NlbCluster [[-HostName] <String>] [[-InterfaceName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NlbCluster** cmdlet gets information about the Network Load Balancing (NLB) cluster.
The information includes the properties, or attributes, that define the cluster and its status.

## EXAMPLES

### Example 1: Get a cluster object from the local NLB cluster
```
PS C:\>Get-NlbCluster
Name                IPAddress           SubnetMask          Mode
----                ---------           ----------          ----
cluster1            3.53.100.100        255.0.0.0           UNICAST
```

This command gets the cluster object for the local NLB cluster.

### Example 2: Get a cluster object for the specified NLB cluster
```
PS C:\>Get-NlbCluster -HostName "Node01"
Name                IPAddress           SubnetMask          Mode
----                ---------           ----------          ----
cluster2            4.53.100.100        255.0.0.0           UNICAST
```

This command gets the cluster object for the NLB cluster that is named Node01.

### Example 3: Get a cluster object for the specified NLB cluster using the specified interface
```
PS C:\>Get-NlbCluster -HostName "Node02" -InterfaceName "Vlan-2"
Name                IPAddress           SubnetMask          Mode
----                ---------           ----------          ----
cluster2            4.53.100.100        255.0.0.0           UNICAST
```

This command gets the cluster object for the NLB cluster that node named Node02 through the interface named Vlan-2.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

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

