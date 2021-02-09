---
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
online version: 
schema: 2.0.0
title: Suspend-NlbClusterNode
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 178195F1-B8D2-4F7C-98D4-578708DC38EE
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Suspend-NlbClusterNode

## SYNOPSIS
Suspends a specific node in a Network Load Balancing (NLB) cluster.

## SYNTAX

### NonPipeline (Default)
```
Suspend-NlbClusterNode [[-HostName] <String>] [-InterfaceName <String>] [<CommonParameters>]
```

### Pipeline
```
Suspend-NlbClusterNode -InputObject <Node[]> [<CommonParameters>]
```

## DESCRIPTION
The **Suspend-NlbClusterNode** cmdlet suspends a specific node in a Network Load Balancing (NLB) cluster.
A node in a cluster may need to be suspended to override any remote control cmdlets, or non-Windows PowerShell® operations, that are issued or for maintenance work.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Suspend-NlbClusterNode -InputObject node2
Name                State               Interface           HostID 
----                -----               ---------           ------ 
node2               Suspended           vlan-3              2
```

This example suspends cluster node named node2 on the local cluster.

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
Specifies the cluster node to suspend.

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

[Stop-NlbClusterNode](./Stop-NlbClusterNode.md)

[Suspend-NlbCluster](./Suspend-NlbCluster.md)

