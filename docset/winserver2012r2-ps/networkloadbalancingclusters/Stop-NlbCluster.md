---
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
online version: 
schema: 2.0.0
title: Stop-NlbCluster
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 4ACF3C94-5AA5-45A5-9E0F-A57EDA1AA5E7
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Stop-NlbCluster

## SYNOPSIS
Stops all nodes of a Network Load Balancing (NLB) cluster.

## SYNTAX

### NonPipeline (Default)
```
Stop-NlbCluster [-Drain] [-Timeout <UInt32>] [[-HostName] <String>] [[-InterfaceName] <String>]
 [<CommonParameters>]
```

### Pipeline
```
Stop-NlbCluster -InputObject <Cluster[]> [-Drain] [-Timeout <UInt32>] [<CommonParameters>]
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
Aliases: D

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
Parameter Sets: NonPipeline
Aliases: Host, HN, H

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster to stop.

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

### -Timeout
Specifies the number of minutes to wait for the drain operation before stopping the cluster.
After the time expires, the existing connections will be dropped.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: T

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

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

