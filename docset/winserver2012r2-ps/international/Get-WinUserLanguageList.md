---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
online version: 
schema: 2.0.0
title: Get-WinUserLanguageList
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: F69CACEE-63A8-4B52-A802-D1AF77E7690C
---

# Get-WinUserLanguageList

## SYNOPSIS
Gets the language list for the current user account.

## SYNTAX

```
Get-WinUserLanguageList [<CommonParameters>]
```

## DESCRIPTION
The **Get-WinUserLanguageList** cmdlet returns the current user language settings.
These settings include input method, spelling setting, text prediction setting, and handwriting input mode.
For more information, see [CultureInfo Class](https://go.microsoft.com/fwlink/?LinkID=242306) and [Manage the input and display language settings in Windows 10](https://support.microsoft.com/help/4496404/windows-10-manage-the-input-and-display-language#input_language).

## EXAMPLES

### Example 1
```
PS C:\>Get-WinUserLanguageList
LanguageTag     : en-US

Autonym         : English (United States) 

EnglishName     : English (United States) 

LocalizedName   : English (United States) 

ScriptName      : Latin

InputMethodTip  : {0409:00000409}

Handwriting     : False 

LanguageTag     : fr-FR

Autonym         : français (France) 

EnglishName     : French (France) 

LocalizedName   : French (France) 

ScriptName      : Latin

InputMethodTip  : {040c:0000040c}

Handwriting     : False
```

This cmdlet returns the current user account's language list together with BCP-47 tags and the corresponding display name.

### Example 2
```
PS C:\>(Get-WinUserLanguageList)[0].InputMethodTip
0409:00000409

0409:00010409
```

This cmdlet returns the list of currently enabled input methods as a TIP string.

### Example 3
```
PS C:\>(Get-WinUserLanguageList)[0].autonym
English (United States)
```

This cmdlet returns the autonym property of the first item in the user's language list.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Collections.Generic.List<Microsoft.InternationalSettings.Commands.WinUserLanguage>
A list of WinUserLanguage objects that contain one or more languages and associated properties from the current user account's language list.
For information about the Generic.List object, see List(Of T) Classhttp://go.microsoft.com/fwlink/?LinkID=243342.

The generic list object supports the following methods:

- Add("BCP-47")
- Insert(index, "BCP-47")
- Remove(Index)

The output language object contains the following properties:

--**BCP-47** (READ). A standard language tag that is used to identify languages. For more information, see the Internet Engineering Task Force (IETF) BCP 47 RFChttp://go.microsoft.com/fwlink/?LinkID=242207.
--**Autonym** (LP database) (READ). The name of the language in the language itself.
--**English name** (LP database) (READ). The name of the language in English.
--**Localized name** (LP database) (READ). The name of the language in the current Windows display language.
--**Script** (LP database) (READ). The writing system of the language.
--**Input methods** (READ/WRITE). A list of input method Tablet Input Panel (TIP) strings that are enabled for this language. The enabled Input methods are listed in the format Language ID: Keyboard layout ID.
--**Handwriting recognition input mode** (READ/WRITE). This value is either 0 (freehand) or 1 (write each character separately).

## NOTES

## RELATED LINKS

[New-WinUserLanguageList](./New-WinUserLanguageList.md)

[Set-WinUserLanguageList](./Set-WinUserLanguageList.md)
