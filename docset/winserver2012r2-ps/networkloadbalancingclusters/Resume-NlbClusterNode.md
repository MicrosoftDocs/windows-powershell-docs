---
author: Kateyanne
description: 
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
manager: jasgro
Module Name: NetworkLoadBalancingClusters
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/networkloadbalancingclusters/resume-nlbclusternode?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-NlbClusterNode
---

# Resume-NlbClusterNode

## SYNOPSIS
Resumes a node in a Network Load Balancing (NLB) cluster.

## SYNTAX

### NonPipeline (Default)
```
Resume-NlbClusterNode [[-HostName] <String>] [[-InterfaceName] <String>] [<CommonParameters>]
```

### Pipeline
```
Resume-NlbClusterNode -InputObject <Node[]> [<CommonParameters>]
```

## DESCRIPTION
The **Resume-NlbClusterNode** cmdlet resumes the node in a Network Load Balancing (NLB) cluster that was suspended.
To override any remote control cmdlets that are issued, a node may need to be suspended and resumed.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Resume-NlbClusterNode
Name                State               Interface           HostID 
----                -----               ---------           ------ 
node2               Stopped             vlan-3              2
```

This example resumes the local cluster node.
The node is in the Stopped state and needs to be started after coming back from the Suspended state.

### EXAMPLE 2
```
PS C:\>Resume-NlbClusterNode -InputObject node3
Name                State               Interface           HostID 
----                -----               ---------           ------ 
node3               Stopped             vlan-3              2
```

This example resumes the cluster node named node3 on the local cluster.
The node is in the Stopped state and needs to be started after coming back from the Suspended state.

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
Specifies the cluster node to resume.

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
Position: 1
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

[Set-NlbClusterNode](./Set-NlbClusterNode.md)

[Start-NlbClusterNode](./Start-NlbClusterNode.md)

[Stop-NlbClusterNode](./Stop-NlbClusterNode.md)

[Suspend-NlbClusterNode](./Suspend-NlbClusterNode.md)

