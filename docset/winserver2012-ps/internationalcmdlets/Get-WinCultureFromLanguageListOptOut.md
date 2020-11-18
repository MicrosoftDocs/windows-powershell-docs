---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
ms.assetid: 4C9DDDB7-7D75-4CD5-8F5E-43CB33DCD21A
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-WinCultureFromLanguageListOptOut

## SYNOPSIS
Gets the Culture (User Locale) from the language list opt-out setting for the current user account.

## SYNTAX

```
Get-WinCultureFromLanguageListOptOut [<CommonParameters>]
```

## DESCRIPTION
The **Get-WinCultureFromLanguageListOptOut** cmdlet gets the Culture (User Locale) override setting for the current user account.
When set to $True, the Culture setting is not updated by changes to the Windows display language.
When set the $False, the Culture setting can be reassigned to match the display language changes any time that the display language changes.
The default setting is $False.

## EXAMPLES

### Example 1: Get the Culture (User Locale) for the current user
```
PS C:\>Get-WinCultureFromLanguageListOptOut
```

This command gets the Culture (User Locale) for the current user.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Boolean
A Boolean value that reports the status of this setting.

## NOTES

## RELATED LINKS

