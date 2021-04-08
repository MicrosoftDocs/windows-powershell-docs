---
author: Kateyanne
external help file: Failoverv2_Cmdlets.xml
manager: dansimp
Module Name: FailoverClusters
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/failoverclusters/get-clusterownernode?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-ClusterOwnerNode

## SYNOPSIS
Gets information about which nodes can own a resource in a failover cluster or information about the order of preference among owner nodes for a clustered role.

## SYNTAX

```
Get-ClusterOwnerNode [-Cluster <String>] [-Group <String>] [-InputObject <PSObject>] [-Resource <String>]
 [-ResourceType <String>]
```

## DESCRIPTION
The **Get-ClusterOwnerNode** cmdlet gets information about which nodes can own a resource in a failover cluster or information about the order of preference among owner nodes for a clustered role.

Settings that control the possible or preferred owners affect the way the cluster responds to the failure of a resource or a clustered role.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-ClusterResource -Cluster "Cluster Disk 1" | Get-ClusterOwnerNode
ClusterObject                           OwnerNodes 
-------------                           ---------- 
Cluster Disk 1                          {node1, node2}
```

This example lists the possible owners for the cluster named Cluster Disk 1 in the local cluster.

### EXAMPLE 2
```
PS C:\>Get-ClusterGroup -Group cluster1FS12 | Get-ClusterOwnerNode
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
Aliases: res

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
Aliases: restype

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

### Microsoft.FailoverClusters.PowerShell.ClusterResourceType

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterOwnerNodeList

## NOTES

## RELATED LINKS

[Set-ClusterOwnerNode](./Set-ClusterOwnerNode.md)

