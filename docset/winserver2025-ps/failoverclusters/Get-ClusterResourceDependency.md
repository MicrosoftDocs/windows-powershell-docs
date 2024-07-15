---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/get-clusterresourcedependency?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ClusterResourceDependency
---

# Get-ClusterResourceDependency

## SYNOPSIS
Gets information about the dependencies that have been configured between clustered resources in a
failover cluster.

## SYNTAX

```
Get-ClusterResourceDependency [[-Resource] <StringCollection>] [-Guid] [-InputObject <PSObject>]
 [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Get-ClusterResourceDependency` cmdlet gets information about the dependencies that have been
configured between clustered resources in a failover cluster. Resource dependencies control the
order in which resources are brought online or taken offline in the cluster.

## EXAMPLES

### Example 1

```powershell
Get-ClusterResourceDependency -Resource cluster1FS12
```

This example displays the dependencies for the resource called `cluster1FS12`.

### Example 2

```powershell
Get-ClusterGroup -Name cluster1FS12 | Get-ClusterResource | Get-ClusterResourceDependency
```

This example displays the dependencies for each resource in the clustered file server resource
group called `cluster1FS12`. Some resources don't have dependencies.

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
Position: 0
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

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResourceDependency

## NOTES

## RELATED LINKS

[Add-ClusterResourceDependency](./Add-ClusterResourceDependency.md)

[Get-ClusterGroup](./Get-ClusterGroup.md)

[Get-ClusterResource](./Get-ClusterResource.md)

[Remove-ClusterResourceDependency](./Remove-ClusterResourceDependency.md)

[Set-ClusterResourceDependency](./Set-ClusterResourceDependency.md)
