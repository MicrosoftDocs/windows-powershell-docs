---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-UevStatus
ms.reviewer:
ms.assetid: 40E80A01-27CF-44BA-BE48-7D552F67FD1C
---

# Get-UevStatus

## SYNOPSIS
Gets the status of the UE-V service.

## SYNTAX

```
Get-UevStatus [<CommonParameters>]
```

## DESCRIPTION
The **Get-UevStatus** cmdlet gets the status of the Microsoft User Experience Virtualization (UE-V) service.
This cmdlet returns whether UE-V is enabled and whether a restart is required.

## EXAMPLES

### Example 1: Get status of the UE-V service
```
PS C:\>Get-UevStatus
```

This command gets the status of the UE-V service.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-Uev](./Disable-Uev.md)

[Enable-Uev](./Enable-Uev.md)

