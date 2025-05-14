---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/international/set-windefaultinputmethodoverride?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WinDefaultInputMethodOverride
---

# Set-WinDefaultInputMethodOverride

## SYNOPSIS
Sets the default input method override for the current user account.

## SYNTAX

```
Set-WinDefaultInputMethodOverride [[-InputTip] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WinDefaultInputMethodOverride** cmdlet sets the default input method override setting, which specifies a default input method for the current user account.
If no override setting is used, the input method is dynamically determined from the language list of the current user account.
For more information, see the **Get-WinUserLanguageList** and **Set-WinUserLanguageList** cmdlets.

## EXAMPLES

### Example 1: Set the default input method override
```
PS C:\> Set-WinDefaultInputMethodOverride -InputTip "0409:00000409"
```

This command sets the default input method override to English (United States) - US.

## PARAMETERS

### -InputTip
Specifies an input tip.

```yaml
Type: String
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

### InputTIP
You can pipe a locale ID and a keyboard language ID (KLID). See [Default Input Profiles (Input Locales) in Windows](/windows-hardware/manufacture/desktop/default-input-locales-for-windows-language-packs)

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WinDefaultInputMethodOverride](./Get-WinDefaultInputMethodOverride.md)
