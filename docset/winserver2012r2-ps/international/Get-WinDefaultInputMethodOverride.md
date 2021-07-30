---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/international/get-windefaultinputmethodoverride?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WinDefaultInputMethodOverride
---

# Get-WinDefaultInputMethodOverride

## SYNOPSIS
Gets the default input method override setting for the current user account.

## SYNTAX

```
Get-WinDefaultInputMethodOverride [<CommonParameters>]
```

## DESCRIPTION
The **Get-WinDefaultInputMethodOverride** cmdlet retrieves the default input method override setting, which specifies a default input method for the current user account. 
If no override setting is used, the input method is dynamically determined from the current user account's language list (see Get-WinUserLanguageList and  Set-WinUserLanguageList).

## EXAMPLES

### Example 1
```
PS C:\>Get-WinDefaultInputMethodOverride
InputMethodTip      Keyboard name

---------------     -------------

0409:00000409       English (United States) - US
```

This command returns and displays the default input method for the current user account.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### WinKeyboardObject
The Tablet Input Panel (TIP) string for the default input method override setting.

## NOTES

## RELATED LINKS

[Set-WinDefaultInputMethodOverride](./Set-WinDefaultInputMethodOverride.md)

