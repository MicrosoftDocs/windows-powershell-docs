---
external help file: StorSpaces2_Cmdlets.xml
Module Name: StorageSpaces
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/storagespaces/repair-spacesconfiguration?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Repair-SpacesConfiguration
---

# Repair-SpacesConfiguration

## SYNOPSIS
Repairs unhealthy resources associated with a Storage Spaces storage pool.

## SYNTAX

```
Repair-SpacesConfiguration
```

## DESCRIPTION
The Repair-SpacesConfiguration cmdlet repairs unhealthy Storage Spaces resources.
It performs the following operations:

Enumerate storage pools that are read-only and offer to recover them

Enumerate storage spaces that are set for manual attachment, and attach them

Enumerate and repair any unhealthy storage spaces

Enumerate and display any unhealthy physical disks

## EXAMPLES

### Example 1 - Repair Storage Spaces
```
PS C:\>Repair-SpacesConfiguration
```

## PARAMETERS

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

