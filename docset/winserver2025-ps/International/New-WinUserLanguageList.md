---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/international/new-winuserlanguagelist?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-WinUserLanguageList
---

# New-WinUserLanguageList

## SYNOPSIS
Instantiates a new language list object.

## SYNTAX

```
New-WinUserLanguageList [-Language] <String> [<CommonParameters>]
```

## DESCRIPTION
The **New-WinUserLanguageList** cmdlet creates a user language list object.
The object settings include input method, spelling setting, text prediction setting, and handwriting input mode.
For more information, see [CultureInfo Class](https://go.microsoft.com/fwlink/?LinkID=242306) and [Configurable Language and Cultural Settings](https://go.microsoft.com/fwlink/?LinkID=242307).

## EXAMPLES

### Example 1: Create and set a language list
```powershell
PS C:\> $UserLanguageList = New-WinUserLanguageList -Language "en-US"
PS C:\> $UserLanguageList.Add("fr-FR")
PS C:\> Set-WinUserLanguageList -LanguageList $UserLanguageList
```

The first command creates a language list that contains US English.
The command stores that object in the $UserLanguageList variable.

The second command adds France French to the object in $UserLanguageList.

The final command assigns the list in $UserLanguageList to the current user account by using the **Set-WinUserLanguageList** cmdlet.

## PARAMETERS

### -Language
Specifies a language.

```yaml
Type: String
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

### System.Collections.Generic.List<Microsoft.InternationalSettings.Commands.WinUserLanguage>
A list of **WinUserLanguage** objects that contain one or more languages and associated properties from the current user account's language list.
For more information about the **Generic.List** object, see [System.Collections.Generic.List(Of T)](https://go.microsoft.com/fwlink/?LinkID=243342).

The generic list object supports the following methods:

- Add("BCP-47")
- Insert(index, "BCP-47")
- Remove(Index)

The **LanguageList** is a list of language objects in the current user account's list.
The language list object contains the following methods:

- **Add** ("BCP-47")
- **Insert** (BCP-47, index)
- **Remove** (BCP-47)
- **Remove** (Index)

The language list object contains the following properties:

- **BCP-47** (READ).
A standard language tag that is used to identify languages.
For more information, see the [Internet Engineering Task Force (IETF) BCP 47 RFC](https://go.microsoft.com/fwlink/?LinkID=242207).
- **Autonym** (LP database) (READ).
The name of the language in the language itself.
- **English name** (LP database) (READ).
The name of the language in English.
- **Localized name** (LP database) (READ).
The name of the language in the current Windows display language.
- **Script** (LP database) (READ).
The writing system of the language.
- **Input methods** (READ/WRITE).
A list of input method Tablet Input Panel (TIP) strings that are enabled for this language.
The enabled input methods are listed in the format `Language ID: Keyboard layout ID`.
- **Handwriting recognition input mode** (READ/WRITE).
This value is either 0 (freehand) or 1 (write each character separately).

## NOTES

## RELATED LINKS

[Get-WinUserLanguageList](./Get-WinUserLanguageList.md)

[Set-WinUserLanguageList](./Set-WinUserLanguageList.md)

