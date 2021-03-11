---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
online version: 
schema: 2.0.0
title: Get-WinUILanguageOverride
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: EBDDEED1-79CD-4383-B4C3-6C7E1E0F4967
---

# Get-WinUILanguageOverride

## SYNOPSIS
Gets the Windows user interface (UI) language override setting for the current user account.

## SYNTAX

```
Get-WinUILanguageOverride [<CommonParameters>]
```

## DESCRIPTION
The **Get-WinUILanguageOverride** cmdlet specifies that a user-preferred display language should be used for the Windows UI.
If no override setting is used, the display language is dynamically determined from the user's language list (see Get-WinUserLanguageList and Set-WinUserLanguageList).

## EXAMPLES

### Example 1
```
PS C:\>Get-WinUILanguageOverride
LCID             Name             DisplayName                                                                        

----             ----             -----------                                                                        

1033             en-US            English (United States)
```

This command gets and displays the UI language override setting for the current user account.
If the Windows UI language override is not set for the current user account, this command returns a null value.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### CultureInfo
An object that contains the Windows UI language override for the current user account.
For more information about the CultureInfo object, see CultureInfo Classhttp://go.microsoft.com/fwlink/?LinkID=242306.

## NOTES

## RELATED LINKS

[Set-WinUILanguageOverride](./Set-WinUILanguageOverride.md)

