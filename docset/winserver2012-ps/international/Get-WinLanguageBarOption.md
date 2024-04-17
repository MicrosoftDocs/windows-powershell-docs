---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
online version: https://learn.microsoft.com/powershell/module/international/get-winlanguagebaroption?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WinLanguageBarOption

## SYNOPSIS
Gets the language bar mode and language bar type for the current user account.

## SYNTAX

```
Get-WinLanguageBarOption [<CommonParameters>]
```

## DESCRIPTION
The **Get-WinLanguageBarOption** cmdlet gets the language bar type and mode by using a LanguageBar object.
The values for the type and mode settings can be either true or false.
The default value for each setting is false.

## EXAMPLES

### Example 1: Get the language bar options for the current user
```
PS C:\>Get-WinLanguageBarOption
IsLegacyLanguageBar    IsLegacySwitchingMode

-------------------    ---------------------

False                  False
```

This command returns the settings for the language bar options for the current user account.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### LanguageBar
A string that reports the language bar mode and type.
Possible values are the following:

- IsLegacyLanguageBar. When this setting is set to true, the desktop language bar is used (where available). When this setting is set to false, the modem input switcher is used (recommended). 
- IsLegacySwitchingMode. When this setting is set to $True, the current input method (keyboard layout or input method editor (IME)) is selected for the current application only. When new applications start, the default input method is selected (see Get-WinDefaultInputMethodOverride). When this setting is set to $False, the input method is selected for all applications and changes only when the user actively switches input methods (recommended).

## NOTES

## RELATED LINKS

