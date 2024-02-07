---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/get-clusterownernode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ClusterOwnerNode
---

# Get-ClusterOwnerNode

## SYNOPSIS
Gets information about which nodes can own a resource in a failover cluster or information about the
order of preference among owner nodes for a clustered role.

## SYNTAX

```
Get-ClusterOwnerNode [-Resource <String>] [-Group <String>] [-ResourceType <String>]
 [-InputObject <PSObject>] [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Get-ClusterOwnerNode` cmdlet gets information about which nodes can own a resource in a
failover cluster or information about the order of preference among owner nodes for a clustered
role.

Settings that control the possible or preferred owners affect the way the cluster responds to the
failure of a resource or a clustered role.

## EXAMPLES

### Example 1

```powershell
Get-ClusterResource -Cluster "Cluster Disk 1" | Get-ClusterOwnerNode
```

This example lists the possible owners for the cluster named `Cluster Disk 1` in the local cluster.

### Example 2

```powershell
Get-ClusterGroup -Group cluster1FS12 | Get-ClusterOwnerNode
```

This example lists the preferred owners for the clustered file server, or resource group, called
`cluster1FS12` on the local cluster.

## PARAMETERS

### -Cluster

Specifies the name of the cluster on which to run this cmdlet. If the input for this parameter is
`.` or it is omitted, then the cmdlet runs on the local cluster.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

### Microsoft.FailoverClusters.PowerShell.ClusterResourceType

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterOwnerNodeList

## NOTES

## RELATED LINKS

[Set-ClusterOwnerNode](./Set-ClusterOwnerNode.md)
