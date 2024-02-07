---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/international/get-winlanguagebaroption?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WinLanguageBarOption
---

# Get-WinLanguageBarOption

## SYNOPSIS
Gets the language bar mode and language bar type for the current user account.

## SYNTAX

```
Get-WinLanguageBarOption [<CommonParameters>]
```

## DESCRIPTION
The **Get-WinLanguageBarOption** cmdlet gets the language bar type and mode by using a **LanguageBar** object.
The values for the type and mode settings can be either true or false.
The default value for each setting is false.

## EXAMPLES

### Example 1: Get the settings for the language bar
```
PS C:\> Get-WinLanguageBarOption
IsLegacyLanguageBar    IsLegacySwitchingMode
-------------------    ---------------------
False                  False
```

This command returns the current settings for the language bar options for the current user account.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### LanguageBar
This cmdlet returns an object that contains the following settings.

- **IsLegacyLanguageBar**.
When this setting is set to true, the desktop language bar is used, where available.
When this setting is set to false, the modem input switcher is used.
This is recommended.
- **IsLegacySwitchingMode**.
When this setting is set to true, the current input method, which includes keyboard layout or input method editor (IME), is selected for the current application only.
When new applications start, the default input method is selected.
For more information, see the **Get-WinDefaultInputMethodOverride** cmdlet.
When this setting is set to false, the input method is selected for all applications and changes only when the user actively switches input methods (recommended).

## NOTES

## RELATED LINKS

[Get-WinDefaultInputMethodOverride](./Get-WinDefaultInputMethodOverride.md)

[Set-WinLanguageBarOption](./Set-WinLanguageBarOption.md)

