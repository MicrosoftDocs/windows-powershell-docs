---
external help file: StorSpaces2_Cmdlets.xml
online version: 
schema: 2.0.0
title: Get-SpacesPool
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: E6606122-2004-4D79-90AC-4EF56A6627FF
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-SpacesPool

## SYNOPSIS
Gets all storage pools on the Storage Spaces subsystem.

## SYNTAX

```
Get-SpacesPool [[-StoragePoolFriendlyName] <String>]
```

## DESCRIPTION
The Get-SpacesPool cmdlet gets all StoragePool objects on the Storage Spaces subsystem.

## EXAMPLES

### Example 1 - Get all storage pools on the Storage Spaces subsystem
```
PS C:\>Get-SpacesPool
FriendlyName            OperationalStatus       HealthStatus            IsPrimordial            IsReadOnly

------------            -----------------       ------------            ------------            ----------

Company Data            OK                      Healthy                 False                   False

Primordial              OK                      Healthy                 True                    False
```

This example gets all storage pools for the Storage Spaces provider.

### Example 2 - Get a particular storage pool
```
PS C:\>Get-SpacesPool -StoragePoolFriendlyName "Music Pool"
```

This example gets the storage pool named "Music Pool".

## PARAMETERS

### -StoragePoolFriendlyName
Specifies the friendly name of the storage pool.

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

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
This cmdlet returns objects representing storage pools

## NOTES

## RELATED LINKS

