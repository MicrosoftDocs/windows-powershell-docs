---
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
online version: 
schema: 2.0.0
title: Add-ClusterResourceDependency
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: EFE27260-9B24-49E8-9906-0249FBD81AFA
---

# Add-ClusterResourceDependency

## SYNOPSIS
Adds a resource to the list of resources on which a particular resource depends, using AND as the connector, within a failover cluster.

## SYNTAX

```
Add-ClusterResourceDependency [[-Resource] <String>] [[-Provider] <String>] [-InputObject <PSObject>]
 [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-ClusterResourceDependency** cmdlet adds a resource to the list of resources on which a particular resource depends, using AND as the connector, within a failover cluster. Existing dependencies will remain on the list. If you specify the *InputObject* parameter, the *Resource* parameter will be ignored.

A dependent resource is brought online after the resources on which it depends.
A dependent resource is taken offline before the resources on which it depends.

## EXAMPLES

### Example 1
```
PS C:\> Add-ClusterResourceDependency -Resource "FileServer-(cluster1FS12)" -Provider "Cluster Disk 4"
Name                State               Group               ResourceType 
----                -----               -----               ------------ 
FileServer-(clus... Online              cluster1FS12        File Server
```

This example adds the resource named "Cluster Disk 4" to the list of resources on which the resource called "FileServer-(cluster1FS12)" depends, using AND as the connector.

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
Specifies the name of the cluster resource for which to add a dependency.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

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
