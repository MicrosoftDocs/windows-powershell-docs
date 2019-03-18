---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
ms.assetid: 30B8E8FC-D5B9-4B13-8EFB-1F7DE07AA465
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
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
For more information, see CultureInfo Classhttp://go.microsoft.com/fwlink/?LinkID=242306 and Configurable Language and Cultural Settingshttp://go.microsoft.com/fwlink/?LinkID=242307.

## EXAMPLES

### Example 1: Get the language list for the current user
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

Autonym         : fran §ais (France) 

EnglishName     : French (France) 

LocalizedName   : French (France) 

ScriptName      : Latin

InputMethodTip  : {040c:0000040c}

Handwriting     : False
```

This command returns the current user account's language list together with BCP-47 tags and the corresponding display name.

### Example 2: Get the currently enabled input methods
```
PS C:\>(Get-WinUserLanguageList)[0].InputMethodTip
0409:00000409

0409:00010409
```

This command returns the list of currently enabled input methods as a TIP string.

### Example 3: Get the autonym property for a user
```
PS C:\>(Get-WinUserLanguageList)[0].autonym
English (United States)
```

This command returns the autonym property of the first item in the user's language list.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Collections.Generic.List<Microsoft.InternationalSettings.Commands.WinUserLanguage>
A list of WinUserLanguage objects that contain one or more languages and associated properties from the current user account's language list.
For information about the Generic.List object, see System.Collections.Generic.List<T\> Classhttp://go.microsoft.com/fwlink/?LinkID=243342.

The generic list object supports the following methods:

- Add("BCP-47")
- Insert(index, "BCP-47")
- Remove(Index)

The output language object contains the following properties:

- BCP-47 (READ). A standard language tag that is used to identify languages. For more information, see the Internet Engineering Task Force (IETF) BCP 47 RFChttp://go.microsoft.com/fwlink/?LinkID=242207. 
- Autonym (LP database) (READ). The name of the language in the language itself. 
- English name (LP database) (READ). The name of the language in English. 
- Localized name (LP database) (READ). The name of the language in the current Windows display language. 
- Script (LP database) (READ). The writing system of the language. 
- Input methods (READ/WRITE). A list of input method Tablet Input Panel (TIP) strings that are enabled for this language. The enabled Input methods are listed in the format Language ID: Keyboard layout ID. 
- Handwriting recognition input mode (READ/WRITE). This value is either 0 (freehand) or 1 (write each character separately).

## NOTES

## RELATED LINKS

