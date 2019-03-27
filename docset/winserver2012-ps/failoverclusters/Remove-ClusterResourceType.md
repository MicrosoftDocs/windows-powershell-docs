---
external help file: Failoverv2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: BC4F51A9-B0EC-4908-B251-C2469FA470A4
manager: dansimp
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Remove-ClusterResourceType

## SYNOPSIS
Removes a resource type from a failover cluster.

## SYNTAX

```
Remove-ClusterResourceType [[-Name] <StringCollection>] [-Cluster <String>] [-InputObject <PSObject>]
```

## DESCRIPTION
The **Remove-ClusterResourceType** cmdlet removes a resource type from a failover cluster.
A resource type is a class of resource, such as physical disk, network name, or virtual machine, that is organized by the failover cluster.
After a resource type is removed from a failover cluster, resources of that type will not be able to be used in the cluster.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-ClusterResourceType -Name ResType1
```

This example removes the registered resource type named ResType1 on the local cluster.

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
Specifies the cluster resource type to remove.

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
Specifies the name of the cluster resource type to remove.

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

### Microsoft.FailoverClusters.PowerShell.ClusterResourceType

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Add-ClusterResourceType](./Add-ClusterResourceType.md)

[Get-ClusterResourceType](./Get-ClusterResourceType.md)

