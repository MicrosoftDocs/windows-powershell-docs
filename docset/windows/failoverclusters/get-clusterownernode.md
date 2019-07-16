---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-ClusterOwnerNode
ms.reviewer:
ms.assetid: C730B479-DEE6-4C34-B1C8-5E40FB23547A
---

# Get-ClusterOwnerNode

## SYNOPSIS
Gets information about which nodes can own a resource in a failover cluster or information about the order of preference among owner nodes for a clustered role.

## SYNTAX

```
Get-ClusterOwnerNode [-Resource <String>] [-Group <String>] [-ResourceType <String>] [-InputObject <PSObject>]
 [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ClusterOwnerNode** cmdlet gets information about which nodes can own a resource in a failover cluster or information about the order of preference among owner nodes for a clustered role.

Settings that control the possible or preferred owners affect the way the cluster responds to the failure of a resource or a clustered role.

## EXAMPLES

### Example 1
```
PS C:\> Get-ClusterResource -Cluster "Cluster Disk 1" | Get-ClusterOwnerNode
ClusterObject                           OwnerNodes 
-------------                           ---------- 
Cluster Disk 1                          {node1, node2}
```

This example lists the possible owners for the cluster named Cluster Disk 1 in the local cluster.

### Example 2
```
PS C:\> Get-ClusterGroup -Group cluster1FS12 | Get-ClusterOwnerNode
ClusterObject                           OwnerNodes 
-------------                           ---------- 
cluster1FS12                            {}
```

This example lists the preferred owners for the clustered file server, or resource group, called cluster1FS12 on the local cluster.

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

### -Group
Specifies the name of the cluster group for which owner nodes are enumerated.

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
Specifies the cluster group or cluster resource on which to enumerate owner nodes.

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

### -Resource
Specifies the name of the cluster resource for which owner nodes are enumerated.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Res

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceType
Specifies the name of the cluster resource type for which owner nodes are enumerated.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ResType

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

### Microsoft.FailoverClusters.PowerShell.ClusterResourceType

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterOwnerNodeList

## NOTES

## RELATED LINKS

[Set-ClusterOwnerNode](./Set-ClusterOwnerNode.md)

