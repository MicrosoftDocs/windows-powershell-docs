---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: kenwith
author: kenwith
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-WinSystemLocale
ms.reviewer:
ms.assetid: AC8FD481-A2CC-43E8-AB48-2721F48B4D9A
---

# Get-WinSystemLocale

## SYNOPSIS
Gets the System-locale setting for the current computer.

## SYNTAX

```
Get-WinSystemLocale [<CommonParameters>]
```

## DESCRIPTION
The **Get-WinSystemLocale** cmdlet returns the current value of the System-locale setting.
The System-locale setting determines which code pages, which include ANSI, DOS, and Macintosh, the computer uses by default.

## EXAMPLES

### Example 1: Get the system locale
```
PS C:\> GET-WinSystemLocale
LCID             Name             DisplayName
----             ----             -----------
1033             en-US            English (United States)
```

This command gets and displays the System-locale setting for the current computer.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### CultureInfo
This cmdlet returns the system locale of the current computer.
For more information about the CultureInfo object, see [CultureInfo Class](http://go.microsoft.com/fwlink/?LinkID=242306).

## NOTES

## RELATED LINKS

[Configurable Language and Cultural Settings](http://go.microsoft.com/fwlink/?LinkID=242307)

[Set-WinSystemLocale](./Set-WinSystemLocale.md)

