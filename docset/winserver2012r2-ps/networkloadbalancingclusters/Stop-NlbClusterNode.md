---
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
online version: 
schema: 2.0.0
title: Stop-NlbClusterNode
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: C7659763-21A6-48A8-9A65-86D22E5200C5
ms.author: v-anbarr
ms.reviewer: brianlic
---

# Stop-NlbClusterNode

## SYNOPSIS
Stops a node in a Network Load Balancing (NLB) cluster.

## SYNTAX

### NonPipeline (Default)
```
Stop-NlbClusterNode [-Drain] [-Timeout <UInt32>] [[-HostName] <String>] [-InterfaceName <String>]
 [<CommonParameters>]
```

### Pipeline
```
Stop-NlbClusterNode -InputObject <Node[]> [-Drain] [-Timeout <UInt32>] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-NlbClusterNode** cmdlet stops a node in a Network Load Balancing (NLB) cluster.
When the nodes are stopped in the cluster, client connections that are already in progress are interrupted.
To avoid interrupting active connections, consider using the **Drain** parameter, which allows the node to continue servicing active connections but disables all new traffic to that node.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Stop-NlbClusterNode node2
Name                State               Interface           HostID 
----                -----               ---------           ------ 
node2               Stopped             vlan-3              2
```

This example stops the cluster node named node2 on the local cluster.

### EXAMPLE 2
```
PS C:\>Stop-NlbClusterNode -Drain -Timeout 10
Name                State               Interface           HostID 
----                -----               ---------           ------ 
node3               Stopped             vlan-3              3
```

This example stops the local cluster node.
Before this cmdlet stops the cluster, this cmdlet drains all existing connections for up to 10 seconds.
During that time, new connections will not be established on this node.
Any remaining connections after the 10 seconds will be forcefully terminated.

## PARAMETERS

### -Drain
Drains existing traffic before stopping the cluster node.
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
Specifies the cluster node to stop.

```yaml
Type: Node[]
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
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Timeout
Specifies the number of seconds to wait for the drain operation before stopping the cluster node.
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

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Node

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Node

## NOTES

## RELATED LINKS

[Add-NlbClusterNode](./Add-NlbClusterNode.md)

[Get-NlbClusterNode](./Get-NlbClusterNode.md)

[Remove-NlbClusterNode](./Remove-NlbClusterNode.md)

[Resume-NlbClusterNode](./Resume-NlbClusterNode.md)

[Set-NlbClusterNode](./Set-NlbClusterNode.md)

[Start-NlbClusterNode](./Start-NlbClusterNode.md)

[Suspend-NlbClusterNode](./Suspend-NlbClusterNode.md)

