---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-WinCultureFromLanguageListOptOut
ms.reviewer:
ms.assetid: E9F34EC5-6F21-4957-87F9-032E11CFDA07
---

# Get-WinCultureFromLanguageListOptOut

## SYNOPSIS
Gets the Culture from the language list opt-out setting for the current user account.

## SYNTAX

```
Get-WinCultureFromLanguageListOptOut [<CommonParameters>]
```

## DESCRIPTION
The **Get-WinCultureFromLanguageListOptOut** cmdlet gets the Culture, or User Locale, override setting for the current user account.
When set to $True, the Culture setting is not updated by changes to the Windows display language.
When set to $False, the Culture setting can be reassigned to match the display language changes any time that the display language changes.
The default setting is $False.

## EXAMPLES

### Example 1: Get the Culture override setting
```
PS C:\> Get-WinCultureFromLanguageListOptOut
```

This command gets the Culture override setting for the current user account.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Boolean
This cmdlet returns a Boolean value that reports the status of this setting.

## NOTES

## RELATED LINKS

[Set-WinCultureFromLanguageListOptOut](./Set-WinCultureFromLanguageListOptOut.md)

