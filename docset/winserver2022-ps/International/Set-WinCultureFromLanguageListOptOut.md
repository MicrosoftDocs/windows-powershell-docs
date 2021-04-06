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
title: Set-WinCultureFromLanguageListOptOut
ms.reviewer:
ms.assetid: 3383B8A3-16DF-45A9-848F-B6A76FFAB900
---

# Set-WinCultureFromLanguageListOptOut

## SYNOPSIS
Sets the Culture from language list opt out setting for the current user account.

## SYNTAX

```
Set-WinCultureFromLanguageListOptOut [-OptOut] <Boolean> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WinCultureFromLanguageListOptOut** cmdlet sets the Culture, or User Locale, opt-out setting for the current user account.
Setting this option to $True disables the action of dynamically setting the Culture for the current user based on changes to the Windows display language.
Setting this option to $False activates the dynamic setting behavior.
The default setting is $False.

## EXAMPLES

### Example 1: Block dynamic setting
```
PS C:\> Set-WinCultureFromLanguageListOptOut -OptOut $True
```

This command blocks the dynamic setting behavior.

## PARAMETERS

### -OptOut
Specifies the opt-out value.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WinCultureFromLanguageListOptOut](./Get-WinCultureFromLanguageListOptOut.md)

