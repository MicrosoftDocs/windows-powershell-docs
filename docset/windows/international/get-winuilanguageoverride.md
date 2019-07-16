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
title: Get-WinUILanguageOverride
ms.reviewer:
ms.assetid: EBDDEED1-79CD-4383-B4C3-6C7E1E0F4967
---

# Get-WinUILanguageOverride

## SYNOPSIS
Gets the Windows UI language override setting for the current user account.

## SYNTAX

```
Get-WinUILanguageOverride [<CommonParameters>]
```

## DESCRIPTION
The **Get-WinUILanguageOverride** cmdlet specifies that a user-preferred display language should be used for the Windows user interface (UI).
If no override setting is used, the display language is dynamically determined from the user language list.
For more information, see the **Get-WinUserLanguageList** and **Set-WinUserLanguageList** cmdlets.

## EXAMPLES

### Example 1: Display the language override setting
```
PS C:\> Get-WinUILanguageOverride
LCID             Name             DisplayName                                                                        
----             ----             -----------                                                                        
1033             en-US            English (United States)
```

This command gets and displays the UI language override setting for the current user account.
If the Windows UI language override is not set for the current user account, this command returns a null value.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### CultureInfo
This cmdlet returns the Windows UI language override for the current user account.
For more information about the **CultureInfo** object, see [CultureInfo Class](http://go.microsoft.com/fwlink/?LinkID=242306).

## NOTES

## RELATED LINKS

[Get-WinUserLanguageList](./Get-WinUserLanguageList.md)

[Set-WinUILanguageOverride](./Set-WinUILanguageOverride.md)

[Set-WinUserLanguageList](./Set-WinUserLanguageList.md)

