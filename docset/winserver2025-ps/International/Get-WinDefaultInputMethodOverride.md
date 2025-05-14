---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/international/get-windefaultinputmethodoverride?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
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
If no override setting is used, the input method is dynamically determined from the language list of the current user account.
For more information, see the **Get-WinUserLanguageList** and **Set-WinUserLanguageList** cmdlets.

## EXAMPLES

### Example 1: Display default input method
```
PS C:\> Get-WinDefaultInputMethodOverride
InputMethodTip      Keyboard name
---------------     -------------
0409:00000409       English (United States) - US
```

This command returns and displays the default input method for the current user account.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### WinKeyboardObject
This cmdlet returns the Tablet Input Panel (TIP) string for the default input method override setting.

## NOTES

## RELATED LINKS

[Set-WinDefaultInputMethodOverride](./Set-WinDefaultInputMethodOverride.md)

