---
external help file: StorSpaces2_Cmdlets.xml
online version: 
schema: 2.0.0
title: Get-AvailableDriveLetter
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 70A9BC86-EFBD-415D-AE2B-5EFA26A3A745
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-AvailableDriveLetter

## SYNOPSIS
Returns an array of the available drive letters.

## SYNTAX

```
Get-AvailableDriveLetter [-ReturnFirstLetterOnly]
```

## DESCRIPTION
Returns an array of all available drive letters, or optionally only the first available drive letter.

## EXAMPLES

### Example 1 - Get all available drive letters
```
PS C:\>Get-AvailableDriveLetter
```

### Example 2 - Get the first available drive letter
```
PS C:\>Get-AvailableDriveLetter -ReturnFirstLetterOnly
```

## PARAMETERS

### -ReturnFirstLetterOnly
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

## INPUTS

### None

## OUTPUTS

### System.String
This cmdlet outputs an array of strings that stores the available drive letters.

## NOTES

## RELATED LINKS

