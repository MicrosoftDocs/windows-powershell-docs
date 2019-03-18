---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
online version: 
schema: 2.0.0
title: Get-WinSystemLocale
ms.author: kenwith
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: AC8FD481-A2CC-43E8-AB48-2721F48B4D9A
---

# Get-WinSystemLocale

## SYNOPSIS
Gets the System-locale setting (that is, the language for non-Unicode programs) for the current computer.

## SYNTAX

```
Get-WinSystemLocale [<CommonParameters>]
```

## DESCRIPTION
The **Get-WinSystemLocale** cmdlet returns the current value of the System-locale setting.
The System-locale setting determines which code pages (ANSI, DOS, and Macintosh) the system uses by default.

## EXAMPLES

### Example 1
```
PS C:\>GET-WinSystemLocale
LCID             Name             DisplayName
----             ----             -----------
1033             en-US            English (United States)
```

This command gets and displays the System-locale setting for the current computer.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### CultureInfo
An object that identifies the current computer's system locale.
For more information about the CultureInfo object, see CultureInfo Classhttp://go.microsoft.com/fwlink/?LinkID=242306.

## NOTES

## RELATED LINKS

[Configurable Language and Cultural Settings](http://go.microsoft.com/fwlink/?LinkID=242307)

[Set-WinSystemLocale](./Set-WinSystemLocale.md)

