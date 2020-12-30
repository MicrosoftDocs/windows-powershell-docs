---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssPoolableDisk
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 33E6003F-361A-4E7E-9B38-AF571619F875
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssPoolableDisk

## SYNOPSIS
Gets disks to use to create storage space.

## SYNTAX

```
Get-WssPoolableDisk [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssPoolableDisk** cmdlet gets objects that represent the physical disks to use to create storage space.

## EXAMPLES

### Example 1: Get poolable disks
```
PS C:\>Get-WssPoolableDisk
```

This command gets objects that represent all of the physical disks available for storage space.

### 1:
```
PS C:\>
```

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.Storage.Disk

## NOTES

## RELATED LINKS

[New-WssStorageSpace](./New-WssStorageSpace.md)

[Add-WssDisksToSpacesPool](./Add-WssDisksToSpacesPool.md)

