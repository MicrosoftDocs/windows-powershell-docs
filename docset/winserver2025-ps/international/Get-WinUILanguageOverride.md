---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/international/get-winuilanguageoverride?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WinUILanguageOverride
---

# Get-WinUILanguageOverride

## SYNOPSIS
Gets the Windows UI language override setting for the current user account.

## SYNTAX

```
Get-WinUILanguageOverride [<CommonParameters>]
```

## DESCRIPTION
The **Get-WinUILanguageOverride** cmdlet displays the user-preferred language override that will be used for the Windows user interface (UI) after a reboot or log off. If the override setting is not used, **Get-WinUILanguageOverride** does not return a value. If a change is pending, the **Get-WinUILanguageOverride** returns the pending value.

For more information, see the **Get-WinUserLanguageList** and **Set-WinUserLanguageList** cmdlets.

## EXAMPLES

### Example 1: Display the language override setting
```
PS C:\> Get-WinUILanguageOverride
LCID             Name             DisplayName
----             ----             -----------
1033             en-US            English (United States)
```

This command gets and displays the UI language override setting for the current user account.
If the Windows UI language override is not set for the current user account, this command returns a null value.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### CultureInfo
This cmdlet returns the Windows UI language override for the current user account.
For more information about the **CultureInfo** object, see [CultureInfo Class](https://go.microsoft.com/fwlink/?LinkID=242306).

## NOTES

## RELATED LINKS

[Get-WinUserLanguageList](./Get-WinUserLanguageList.md)

[Set-WinUILanguageOverride](./Set-WinUILanguageOverride.md)

[Set-WinUserLanguageList](./Set-WinUserLanguageList.md)

