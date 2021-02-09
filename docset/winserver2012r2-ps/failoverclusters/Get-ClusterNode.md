---
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
online version: 
schema: 2.0.0
title: Get-ClusterNode
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 6349B139-3EE2-4998-B5C7-386E51A88F84
---

# Get-ClusterNode

## SYNOPSIS
Gets information about one or more nodes, or servers, in a failover cluster.

## SYNTAX

```
Get-ClusterNode [[-Name] <StringCollection>] [-InputObject <PSObject>] [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ClusterNode** cmdlet gets information about one or more nodes, or servers, in a failover cluster.

Use this cmdlet to obtain information about the node status.
To see the resources currently owned by a particular node, specify that node in this cmdlet and then pipe the results through the Get-ClusterResource cmdlet.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-ClusterNode
Name           ID    State 
----           --    ----- 
node1           1     Up 
node2           2     Up 
node3           3     Up 
node4           4     Up
```

This example displays the name, id, and state of each node, or server, in the local cluster.

### EXAMPLE 2
```
PS C:\>Get-ClusterNode -Cluster cluster1
Name           ID    State 
----           --    ----- 
node1           1     Up 
node2           2     Up
```

This example displays the name, id, and state of each node, or server, in the cluster named cluster1.

### EXAMPLE 3
```
PS C:\>Get-ClusterNode -Name node1 | Get-ClusterResource
Name                State               Group               ResourceType 
----                -----               -----               ------------ 
Cluster Disk 1      Online              Cluster Group       Physical Disk 
Cluster IP Address  Online              Cluster Group       IP Address 
Cluster IP Addre... Online              Cluster Group       IPv6 Address 
Cluster Name        Online              Cluster Group       Network Name 
File Share Witness  Offline             Cluster Group       File Share Witness
```

This example lists all cluster resources that are currently owned by node named node1 on the local cluster.

## PARAMETERS

### -Cluster
Specifies the name of the cluster on which to run this cmdlet.
If the input for this parameter is `.` or it is omitted, then the cmdlet runs on the local cluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster on which to enumerate cluster nodes.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the cluster node to get.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterNode

## NOTES

## RELATED LINKS

[Add-ClusterNode](./Add-ClusterNode.md)

[Get-ClusterResource](./Get-ClusterResource.md)

[Remove-ClusterNode](./Remove-ClusterNode.md)

[Resume-ClusterNode](./Resume-ClusterNode.md)

[Start-ClusterNode](./Start-ClusterNode.md)

[Stop-ClusterNode](./Stop-ClusterNode.md)

[Suspend-ClusterNode](./Suspend-ClusterNode.md)

