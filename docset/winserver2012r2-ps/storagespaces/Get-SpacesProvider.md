---
external help file: StorSpaces2_Cmdlets.xml
online version: 
schema: 2.0.0
title: Get-SpacesProvider
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 87D360C3-20F3-4AD8-BD14-81034EE239F6
ms.author: v-anbarr
ms.reviewer: brianlic
---

# Get-SpacesProvider

## SYNOPSIS
Gets the storage provider for Storage Spaces.

## SYNTAX

```
Get-SpacesProvider
```

## DESCRIPTION
The Get-SpacesProvider cmdlet gets the StorageProvider object for the Storage Spaces subsystem, which you can then use with cmdlets from the Storage module.

## EXAMPLES

### Example 1 - Get the Storage Spaces provider
```
PS C:\>Get-SpacesProvider
```

## PARAMETERS

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageProvider
This cmdlet returns an object that represents the storage provider for Storage Spaces.

## NOTES
* This cmdlet is similar to the Get-StorageProvider cmdlet of the Storage module, except that instead of getting all storage providers, the Get-SpacesProvider cmdlet gets only the Storage Spaces provider.

## RELATED LINKS

