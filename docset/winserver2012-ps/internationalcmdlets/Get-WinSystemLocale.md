---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
ms.assetid: 63535C17-EF32-4B51-ABE2-29406605ADB6
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-WinSystemLocale

## SYNOPSIS
Gets the system-locale setting (that is, the language for non-Unicode programs) for the current computer.

## SYNTAX

```
Get-WinSystemLocale [<CommonParameters>]
```

## DESCRIPTION
The **Get-WinSystemLocale** cmdlet returns the current value of the system-locale setting.
The system-locale setting determines which code pages (ANSI, DOS, and Macintosh) the system uses by default.

## EXAMPLES

### Example 1: Get the system-locale setting for the current computer
```
PS C:\>Get-WinSystemLocale
LCID             Name             DisplayName
----             ----             -----------
1033             en-US            English (United States)
```

This command gets and displays the system-locale setting for the current computer.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### CultureInfo
An object that identifies the current computer's system locale.
For more information about the CultureInfo object, see CultureInfo Classhttp://go.microsoft.com/fwlink/?LinkID=242306.

## NOTES

## RELATED LINKS

[Manage the input and display language settings in Windows 10](https://support.microsoft.com/help/4496404/windows-10-manage-the-input-and-display-language#input_language)

