---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
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
title: Get-WinAcceptLanguageFromLanguageListOptOut
ms.reviewer:
ms.assetid: BD5F0FA6-1F7D-482D-B386-C9E8C8CF868F
---

# Get-WinAcceptLanguageFromLanguageListOptOut

## SYNOPSIS
Gets the HTTP Accept Language from the Language List opt-out setting for the current user account.

## SYNTAX

```
Get-WinAcceptLanguageFromLanguageListOptOut [<CommonParameters>]
```

## DESCRIPTION
The **Get-WinAcceptLanguageFromLanguageListOptOut** cmdlet gets the **HTTP Accept Language from Language List opt-out** setting for the current user account.
By default, the **HTTP Accept Language List** is automatically generated from the language list of the current user account.

When set to $True, this setting deletes the current content of the **HTTP Accept Language** registry key and prevents changes to the language list from reestablishing the key.
When set to $False, this setting reestablishes the **HTTP Accept Language List** that is based on the language list for the current user account.

## EXAMPLES

### Example 1: Get the status of the setting
```
PS C:\> Get-WinAcceptLanguageFromLanguageListOptOut
TRUE
```

This command returns the status of the **HTTP Accept Language from Language List opt-out** setting for the current user account.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Boolean
This cmdlet returns a Boolean value that reports the status of the **HTTP Accept Language from Language List opt-out** setting for the current user account.

## NOTES

## RELATED LINKS

[Set-WinAcceptLanguageFromLanguageListOptOut](./Set-WinAcceptLanguageFromLanguageListOptOut.md)

[Get-WinUserLanguageList](./Get-WinUserLanguageList.md)

