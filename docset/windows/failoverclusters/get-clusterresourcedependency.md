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
title: Get-ClusterResourceDependency
ms.reviewer:
ms.assetid: 6342B4AA-8AF6-47C5-81F8-4C21B708CF43
---

# Get-ClusterResourceDependency

## SYNOPSIS
Gets information about the dependencies that have been configured between clustered resources in a failover cluster.

## SYNTAX

```
Get-ClusterResourceDependency [[-Resource] <StringCollection>] [-Guid] [-InputObject <PSObject>]
 [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ClusterResourceDependency** cmdlet gets information about the dependencies that have been configured between clustered resources in a failover cluster.
Resource dependencies control the order in which resources are brought online or taken offline in the cluster.

## EXAMPLES

### Example 1
```
PS C:\> Get-ClusterResourceDependency -Resource cluster1FS12
Resource                                DependencyExpression 
--------                                -------------------- 
cluster1FS12                            [IP Address 172.24.11.0] or [IP Add ...
```

This example displays the dependencies for the resource called cluster1FS12.

### Example 2
```
PS C:\> Get-ClusterGroup -Name cluster1FS12 | Get-ClusterResource | Get-ClusterResourceDependency
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
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

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

