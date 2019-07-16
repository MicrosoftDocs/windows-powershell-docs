---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
online version: 
schema: 2.0.0
title: Get-WinAcceptLanguageFromLanguageListOptOut
ms.author: v-anbarr
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
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
By default, the **HTTP Accept Language List** is automatically generated from the current user account's language list.

When set to TRUE, this setting deletes the current content of the HTTP Accept Language registry key and prevents changes to the language list from reestablishing the key.
When set to FALSE, this setting reestablishes the HTTP Accept Language List that is based on the language list for the current user account.

## EXAMPLES

### Example 1
```
PS C:\>Get-WinAcceptLanguageFromLanguageListOptOut
TRUE
```

This command returns the status of the **HTTP Accept Language from Language List opt-out** setting for the current user account.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Boolean
A Boolean value that reports the status of the **HTTP Accept Language from Language List opt-out** setting for the current user account.

## NOTES

## RELATED LINKS

[Set-WinAcceptLanguageFromLanguageListOptOut](./Set-WinAcceptLanguageFromLanguageListOptOut.md)

[Get-WinUserLanguageList](./Get-WinUserLanguageList.md)

