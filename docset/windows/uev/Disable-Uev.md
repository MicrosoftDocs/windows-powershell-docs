---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Disable-Uev
ms.reviewer:
ms.assetid: 94F7B3CE-A7DB-4709-BF35-DB1395C54D32
---

# Disable-Uev

## SYNOPSIS
Disables the UE-V service.

## SYNTAX

```
Disable-Uev [<CommonParameters>]
```

## DESCRIPTION
The **Disable-Uev** cmdlet disables the Microsoft User Experience Virtualization (UE-V) service on Windows 10 Anniversary edition computers.
This cmdlet disables synchronization of all UE-V settings.
The cmdlet returns a success message.

## EXAMPLES

### Example 1: Disable the UE-V service
```
PS C:\>Disable-Uev
```

This command disables the UE-V service.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-Uev](./Enable-Uev.md)

[Get-UevStatus](./Get-UevStatus.md)

