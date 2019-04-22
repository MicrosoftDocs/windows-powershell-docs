---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
online version: 
schema: 2.0.0
title: Set-WinCultureFromLanguageListOptOut
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
ms.assetid: 3383B8A3-16DF-45A9-848F-B6A76FFAB900
---

# Set-WinCultureFromLanguageListOptOut

## SYNOPSIS
Sets the Culture (User Locale) from language list opt out setting for the current user account.

## SYNTAX

```
Set-WinCultureFromLanguageListOptOut [-OptOut] <Boolean> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WinCultureFromLanguageListOptOut** cmdlet gets the Culture (User Locale) opt-out setting for the current user account.
Setting this option to TRUE disables the action of dynamically setting the Culture (User Locale) for the current user based on changes to the Windows display language.
Setting this option to FALSE activates the dynamic setting behavior.
The default setting is FALSE.

## EXAMPLES

### Example 1
```
PS C:\>Set-WinCultureFromLanguageListOptOut 1
```

This cmdlet blocks the dynamic setting behavior.

## PARAMETERS

### -OptOut


```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WinCultureFromLanguageListOptOut](./Get-WinCultureFromLanguageListOptOut.md)

