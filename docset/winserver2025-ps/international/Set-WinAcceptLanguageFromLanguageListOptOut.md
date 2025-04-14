---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/international/set-winacceptlanguagefromlanguagelistoptout?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WinAcceptLanguageFromLanguageListOptOut
---

# Set-WinAcceptLanguageFromLanguageListOptOut

## SYNOPSIS
Sets the HTTP Accept Language from the Language List opt-out setting for the current user account.

## SYNTAX

```
Set-WinAcceptLanguageFromLanguageListOptOut [-OptOut] <Boolean> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WinAcceptLanguageFromLanguageListOptOut** cmdlet sets the **HTTP Accept Language** from the Language List opt-out setting for the current user account.
By default, the **HTTP Accept Language List** is automatically generated from language list of the current user account.
You can use this cmdlet to set the **HTTP Accept Language from Language List opt-out** value.
When set to $True, this setting deletes the current content of the HTTP Accept Language registry key and prevents changes to the language list from reestablishing the key.
When set to $False, this setting reestablishes the **HTTP Accept Language List** based on the language list for the current user account.

## EXAMPLES

### Example 1: Update the registry key
```
PS C:\> Set-WinAcceptLanguageFromLanguageListOptOut -OptOut $True
```

This cmdlet deletes the current content of the **HTTP Accept Language** registry key and blocks updates to the key based on changes to the language list of the user.

## PARAMETERS

### -OptOut
Specifies the opt-out value.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WinAcceptLanguageFromLanguageListOptOut](./Get-WinAcceptLanguageFromLanguageListOptOut.md)

