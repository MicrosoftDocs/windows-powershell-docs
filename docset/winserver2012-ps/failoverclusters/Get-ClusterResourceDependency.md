---
external help file: Failoverv2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 6342B4AA-8AF6-47C5-81F8-4C21B708CF43
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-ClusterResourceDependency

## SYNOPSIS
Gets information about the dependencies that have been configured between clustered resources in a failover cluster.

## SYNTAX

```
Get-ClusterResourceDependency [[-Resource] <StringCollection>] [-Cluster <String>] [-Guid]
 [-InputObject <PSObject>]
```

## DESCRIPTION
The **Get-ClusterResourceDependency** cmdlet gets information about the dependencies that have been configured between clustered resources in a failover cluster.
Resource dependencies control the order in which resources are brought online or taken offline in the cluster.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-ClusterResourceDependency -Resource cluster1FS12
Resource                                DependencyExpression 
--------                                -------------------- 
cluster1FS12                            [IP Address 172.24.11.0] or [IP Add ...
```

This example displays the dependencies for the resource called cluster1FS12.

### EXAMPLE 2
```
PS C:\>Get-ClusterGroup -Name cluster1FS12 | Get-ClusterResource | Get-ClusterResourceDependency
Resource                                DependencyExpression 
--------                                -------------------- 
cluster1FS12                            [IP Address 172.24.11.0] or [IP Add ... 
 
Cluster Disk 6 
IP Address 157.56.48.0 
IP Address 2001:4898:9:2:: 
IP Address 2002:9d38:31ca:8::
```

This example displays the dependencies for each resource in the clustered file server ─resource group─ called cluster1FS12.
Some resources do not have dependencies.

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

### -Guid
Causes the generated dependency expression to have the resource GUIDs instead of the resource names.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster resource for which to get the dependency expression.

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
Specifies the name of the cluster resource for which to get the dependency expression.

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

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResourceDependency

## NOTES

## RELATED LINKS

[Add-ClusterResourceDependency](./Add-ClusterResourceDependency.md)

[Get-ClusterGroup](./Get-ClusterGroup.md)

[Get-ClusterResource](./Get-ClusterResource.md)

[Remove-ClusterResourceDependency](./Remove-ClusterResourceDependency.md)

[Set-ClusterResourceDependency](./Set-ClusterResourceDependency.md)

