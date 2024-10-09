---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/international/set-winuilanguageoverride?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WinUILanguageOverride
---

# Set-WinUILanguageOverride

## SYNOPSIS
Sets the Windows UI language override setting for the current user account.

## SYNTAX

```
Set-WinUILanguageOverride [[-Language] <CultureInfo>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WinUILanguageOverride** cmdlet sets a user-preferred display language to be used for the Windows user interface (UI).
If no override setting is used, the display language is dynamically determined from the language list of the user. Log off and loging back on is required for changes to take place.

For more information, see the **Get-WinUserLanguageList** and **Set-WinUserLanguageList** cmdlets.

## EXAMPLES

### Example 1: Set a language override
```
PS C:\> Set-WinUILanguageOverride -Language de-DE
```

This command sets the Windows UI language override to German (Germany) for the current user account.

### Example 2: Set a language override to null
```
PS C:\> Set-WinUILanguageOverride
```

This command sets the Windows UI language override to null for the current user account.


## PARAMETERS

### -Language
Specifies a language.

```yaml
Type: CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### CultureInfo
You can pipe an object that contains the Windows UI language override for the current user account.
For more information about the **CultureInfo** object, see [CultureInfo Class](https://go.microsoft.com/fwlink/?LinkID=242306).

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WinUILanguageOverride](./Get-WinUILanguageOverride.md)

[Get-WinUserLanguageList](./Get-WinUserLanguageList.md)

[Set-WinUserLanguageList](./Set-WinUserLanguageList.md)
