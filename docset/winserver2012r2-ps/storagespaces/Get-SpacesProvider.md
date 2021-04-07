---
author: Kateyanne
description: 
external help file: StorSpaces2_Cmdlets.xml
manager: jasgro
Module Name: StorageSpaces
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/storagespaces/get-spacesprovider?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SpacesProvider
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

