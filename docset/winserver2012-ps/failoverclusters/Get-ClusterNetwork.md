---
external help file: Failoverv2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: BC7E8823-6E63-4DFB-8675-81CD5E76F4D7
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-ClusterNetwork

## SYNOPSIS
Gets information about one or more networks in a failover cluster.

## SYNTAX

```
Get-ClusterNetwork [[-Name] <StringCollection>] [-Cluster <String>] [-InputObject <PSObject>]
```

## DESCRIPTION
The **Get-ClusterNetwork** cmdlet gets information about one or more networks in a failover cluster.
A failover cluster requires network connectivity among nodes and between clients and nodes.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-ClusterNetwork
Name                                                                      State 
----                                                                      ----- 
Cluster Network 1                                                            Up 
Cluster Network 2                                                            Up 
Cluster Network 3                                                            Up
```

This example gets information about the networks used by the local cluster.

### Example 2
```
PS C:\>(Get-ClusterNetwork -Name "Cluster Network 1").Name = "Cluster Network 3"
```

This example renames Cluster Network 1 to Cluster Network 3.

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
Specifies the cluster on which to enumerate the cluster networks.

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
Specifies the name of the cluster network to get.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterNetwork

## NOTES

## RELATED LINKS

[Get-ClusterNetworkInterface](./Get-ClusterNetworkInterface.md)

