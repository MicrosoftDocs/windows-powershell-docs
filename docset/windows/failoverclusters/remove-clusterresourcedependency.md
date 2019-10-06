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
title: Remove-ClusterResourceDependency
ms.reviewer:
ms.assetid: CF2A8410-EE45-4493-872B-E5F82E478601
---

# Remove-ClusterResourceDependency

## SYNOPSIS
Removes a dependency between two resources in a clustered role within a failover cluster.

## SYNTAX

```
Remove-ClusterResourceDependency [[-Resource] <String>] [[-Provider] <String>] [-InputObject <PSObject>]
 [-Cluster <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-ClusterResourceDependency** cmdlet removes a dependency between two resources in a clustered role within a failover cluster.

A dependent resource is brought online after the resources on which it depends.
Likewise, a dependent resource is taken offline before the resources on which it depends.
If no dependency is configured between clustered resources, then the order in which they are brought online or taken offline might vary.

## EXAMPLES

### Example 1
```
PS C:\> Remove-ClusterResourceDependency -Resource cluster1FS -Provider "IP Address 2001:4898:9:2:: (3)"
Name                State               Group               ResourceType 
----                -----               -----               ------------ 
cluster1FS          Online              cluster1FS          Network Name
```

This example removes the dependency between cluster resource cluster1FS and the resource named IP Address 2001:4898:9:2:: (3).

### Example 2
```
PS C:\> Get-ClusterResource -Name cluster1FS | Remove-ClusterResourceDependency -Provider "IP Address 2001:4898:9:2:: (3)"
Name                State               Group               ResourceType 
----                -----               -----               ------------ 
cluster1FS          Online              cluster1FS          Network Name
```

This example removes the dependency between the cluster resource named cluster1FS and the resource named IP Address 2001:4898:9:2:: (3).

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster resource from which to remove the dependency.

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
Specifies the cluster resource on which to remove a dependency.

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
Specifies the name of the cluster resource from which to remove the dependency.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## NOTES

## RELATED LINKS

[Add-ClusterResourceDependency](./Add-ClusterResourceDependency.md)

[Get-ClusterResourceDependency](./Get-ClusterResourceDependency.md)

[Set-ClusterResourceDependency](./Set-ClusterResourceDependency.md)

