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
online version: https://docs.microsoft.com/powershell/module/storagespaces/get-spacessubsystem?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SpacesSubsystem
---

# Get-SpacesSubsystem

## SYNOPSIS
Gets the storage subsystem for Storage Spaces.

## SYNTAX

```
Get-SpacesSubsystem
```

## DESCRIPTION
The Get-SpacesSubsystem cmdlet gets the StorageSubsystem object for the Storage Spaces subsystem, which you can then use with cmdlets from the Storage module.

StorageSubsystem object is used as an input on some Storage Management cmdlets.
This cmdlet differs from the Get-StorageSubSystem cmdlet in that it only reports the storage subsystem for Storage Spaces, as opposed to all available storage subsystems.

## EXAMPLES

### Example 1 - Get the StorageSubsystem object for Storage Spaces
```
PS C:\>Get-SpacesSubsystem
```

This example gets the StorageSubsystem object for Storage.

## PARAMETERS

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubSystem
This cmdlet returns an object that represents the Storage Spaces storage subsystem.

## NOTES
* This cmdlet is similar to the Get-StorageSubsystem cmdlet of the Storage module, except that instead of getting all storage subsystems, the Get-SpacesSubsystem cmdlet gets only the Storage Spaces storage subsystem object.

## RELATED LINKS

