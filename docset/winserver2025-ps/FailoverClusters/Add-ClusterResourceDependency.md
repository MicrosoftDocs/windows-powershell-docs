---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/add-clusterresourcedependency?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-ClusterResourceDependency
---

# Add-ClusterResourceDependency

## SYNOPSIS
Adds a resource to the list of resources on which a particular resource depends, using AND as the
connector, within a failover cluster.

## SYNTAX

```
Add-ClusterResourceDependency [[-Resource] <String>] [[-Provider] <String>]
 [-InputObject <PSObject>] [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Add-ClusterResourceDependency` cmdlet adds a resource to the list of resources on which a
particular resource depends, using AND as the connector, within a failover cluster. Existing
dependencies will remain on the list. If you specify the **InputObject** parameter, the **Resource**
parameter will be ignored.

A dependent resource is brought online after the resources on which it depends. A dependent resource
is taken offline before the resources on which it depends.

## EXAMPLES

### Example 1

```powershell
Add-ClusterResourceDependency -Resource "FileServer-(cluster1FS12)" -Provider "Cluster Disk 4"
```

This example adds the resource named `Cluster Disk 4` to the list of resources on which the resource
called `FileServer-(cluster1FS12)` depends.

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

### -InputObject

Specifies the cluster resource for which to add the dependency.

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

### -Provider

Specifies the cluster resource to add as a dependency.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Resource

Specifies the name of the cluster resource for which to add the dependency.

```yaml
Type: String
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

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## NOTES

## RELATED LINKS

[Get-ClusterResourceDependency](./Get-ClusterResourceDependency.md)

[Get-ClusterResourceDependencyReport](./Get-ClusterResourceDependencyReport.md)

[Remove-ClusterResourceDependency](./Remove-ClusterResourceDependency.md)

[Set-ClusterResourceDependency](./Set-ClusterResourceDependency.md)
