---
external help file: Failoverv2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 7B7673AB-20A6-406D-A955-267E42D2F03E
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-ClusterSharedVolume

## SYNOPSIS
Gets information about Cluster Shared Volumes in a failover cluster.

## SYNTAX

```
Get-ClusterSharedVolume [[-Name] <StringCollection>] [-Cluster <String>] [-InputObject <PSObject>]
```

## DESCRIPTION
The **Get-ClusterSharedVolume** cmdlet gets information about Cluster Shared Volumes in a failover cluster.

## EXAMPLES

### Example 1
```
PS C:\>Get-ClusterSharedVolume
Name                       State                      Node 
----                       -----                      ---- 
Cluster Disk 3             Online                     node1 
Cluster Disk 4             Online                     node2
```

This example lists all the Cluster Shared Volumes on the local cluster.

### Example 2
```
PS C:\>Get-ClusterSharedVolume -Cluster cluster1
Name                       State                      Node 
----                       -----                      ---- 
Cluster Disk 1             Online                     node4
```

This example lists all the Cluster Shared Volumes on the cluster named cluster1.

### Example 3
```
PS C:\>Get-ClusterSharedVolume -Name "Cluster Disk 4"
Name                       State                      Node 
----                       -----                      ---- 
Cluster Disk 4             Online                     node2
```

This example displays the state of the Cluster Shared Volume called Cluster Disk 4.

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
Specifies the cluster on which to enumerate the Cluster Shared Volumes.

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
Specifies the name of the Cluster Shared Volume to get.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterSharedVolume

## NOTES

## RELATED LINKS

[Add-ClusterSharedVolume](./Add-ClusterSharedVolume.md)

[Move-ClusterSharedVolume](./Move-ClusterSharedVolume.md)

[Remove-ClusterSharedVolume](./Remove-ClusterSharedVolume.md)

