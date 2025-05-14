---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/international/get-winsystemlocale?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WinSystemLocale
---

# Get-WinSystemLocale

## SYNOPSIS
Gets the System-locale setting for the current computer.

## SYNTAX

```
Get-WinSystemLocale [<CommonParameters>]
```

## DESCRIPTION
The **Get-WinSystemLocale** cmdlet returns the current value of the System-locale setting.
The System-locale setting determines which code pages, which include ANSI, DOS, and Macintosh, the computer uses by default.

## EXAMPLES

### Example 1: Get the system locale
```
PS C:\> GET-WinSystemLocale
LCID             Name             DisplayName
----             ----             -----------
1033             en-US            English (United States)
```

This command gets and displays the System-locale setting for the current computer.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### CultureInfo
This cmdlet returns the system locale of the current computer.
For more information about the CultureInfo object, see [CultureInfo Class](https://go.microsoft.com/fwlink/?LinkID=242306).

## NOTES

## RELATED LINKS

[Manage the input and display language settings in Windows 10](https://support.microsoft.com/help/4496404/windows-10-manage-the-input-and-display-language#input_language)

[Set-WinSystemLocale](./Set-WinSystemLocale.md)

