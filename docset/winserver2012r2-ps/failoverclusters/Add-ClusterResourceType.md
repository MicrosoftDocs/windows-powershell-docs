---
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
online version: 
schema: 2.0.0
title: Add-ClusterResourceType
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 5093EE4B-2C1E-4F89-AAC7-EECBDE3CA59B
---

# Add-ClusterResourceType

## SYNOPSIS
Adds a resource type to a failover cluster, and specifies information such as the dynamic-link library (DLL) to use with that resource type.

## SYNTAX

```
Add-ClusterResourceType [-Name] <String> [-Dll] <String> [[-DisplayName] <String>] [-InputObject <PSObject>]
 [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-ClusterResourceType** cmdlet adds a resource type to a failover cluster, and specifies information such as the dynamic-link library (DLL) to use with that resource type.

The failover cluster software provides Resource DLL files for the most common types of resources.
Using the application programming interface (API) provided in the Microsoft Platform Software Development Kit (SDK), other vendors can add support for other resource types.

Note: This cmdlet cannot be run remotely without Credential Security Service Provider (CredSSP) authentication on the server computer.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Add-ClusterResourceType -Name ResType3 -InputObject C:\res3.dll
Name                                    DisplayName 
----                                    ----------- 
ResType3                                ResType3
```

This example creates ResType3 on the local cluster using res3.dll located on the provided resource DLL file path C:\.

### EXAMPLE 2
```
PS C:\>Add-ClusterResourceType -Name ResType4 -InputObject C:\res4.dll -DisplayName "Resource Type 4"
Name                                    DisplayName 
----                                    ----------- 
ResType4                                Resource Type 4
```

This example creates ResType4 on the local cluster using res4.dll located on the provided resource DLL file path C:\.
The display name of the resource type is Resource Type 4.

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

### -DisplayName
Specifies the display name for the resource type.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Dll
Specifies the DLL file path for the resource type.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster on which to register the new resource type.

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
Specifies the name of the cluster resource type to register.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResourceType

## NOTES

## RELATED LINKS

[Get-ClusterResourceType](./Get-ClusterResourceType.md)

[Remove-ClusterResourceType](./Remove-ClusterResourceType.md)

