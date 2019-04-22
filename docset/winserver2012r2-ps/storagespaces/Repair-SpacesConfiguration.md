---
external help file: StorSpaces2_Cmdlets.xml
online version: 
schema: 2.0.0
title: Repair-SpacesConfiguration
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: C3B44650-848B-4DFA-9F93-730FC7B8A403
ms.author: kenwith
ms.reviewer: brianlic
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

