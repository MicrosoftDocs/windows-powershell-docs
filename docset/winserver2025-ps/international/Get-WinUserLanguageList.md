---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/international/get-winuserlanguagelist?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WinUserLanguageList
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

### Example 1: Get language list for the current account
```
PS C:\> Get-WinUserLanguageList
LanguageTag     : en-US
Autonym         : English (United States)
EnglishName     : English (United States)
LocalizedName   : English (United States)
ScriptName      : Latin
InputMethodTips : {0409:00000409}
Handwriting     : False
LanguageTag     : fr-FR
Autonym         : français (France)
EnglishName     : French (France)
LocalizedName   : French (France)
ScriptName      : Latin
InputMethodTips : {040c:0000040c}
Handwriting     : False
```

This command returns the language list for the current user account, BCP-47 tags, and the corresponding display name.

### Example 2: Display input methods
```
PS C:\> (Get-WinUserLanguageList)[0].InputMethodTips
0409:00000409
0409:00010409
```

This command returns the list of currently enabled input methods as a TIP string.

### Example 3: Display an autonym property
```
PS C:\> (Get-WinUserLanguageList)[0].autonym
English (United States)
```

This command returns the autonym property of the first item in the user language list.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Collections.Generic.List<Microsoft.InternationalSettings.Commands.WinUserLanguage>
This cmdlet returns a list of **WinUserLanguage** objects that contain one or more languages and associated properties from the current user account's language list.
For information about the **Generic.List** object, see [List(Of T) Class](https://go.microsoft.com/fwlink/?LinkID=243342).

The generic list object supports the following methods:

- Add("`LanguageTag`")
- Insert(index, "`LanguageTag`")
- Remove(Index)

The output language object contains the following properties:

- **LanguageTag** (READ).
A standard BCP-47 language tag that is used to identify languages.
For more information, see the [Internet Engineering Task Force (IETF) BCP 47 RFC](https://go.microsoft.com/fwlink/?LinkID=242207).
- **Autonym** (LP database) (READ).
The name of the language in the language itself.
- **EnglishName** (LP database) (READ).
The name of the language in English.
- **LocalizedName** (LP database) (READ).
The name of the language in the current Windows display language.
- **ScriptName** (LP database) (READ).
The writing system of the language.
- **InputMethodTips** (READ/WRITE).
A list of input method Tablet Input Panel (TIP) strings that are enabled for this language.
The enabled Input methods are listed in the format `Language ID: Keyboard layout ID`.
- **Handwriting** (READ/WRITE).
This value is either 0 (freehand) or 1 (write each character separately).

## NOTES

## RELATED LINKS

[New-WinUserLanguageList](./New-WinUserLanguageList.md)

[Set-WinUserLanguageList](./Set-WinUserLanguageList.md)
