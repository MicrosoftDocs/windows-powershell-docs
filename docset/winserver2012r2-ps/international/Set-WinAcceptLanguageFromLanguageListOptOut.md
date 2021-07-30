---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/international/set-winacceptlanguagefromlanguagelistoptout?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
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
By default, the **HTTP Accept Language List** is automatically generated from the current user account's language list.
You can use the **Set-WinAcceptLanguageFromLanguageListOptOut** cmdlet to set the **HTTP Accept Language from Language List opt-out** value. 
When set to TRUE, this setting deletes the current content of the HTTP Accept Language registry key and prevents changes to the language list from reestablishing the key.
When set to FALSE, this setting reestablishes the HTTP Accept Language List based on the language list for the current user account.

## EXAMPLES

### Example 1
```
PS C:\> Set-WinAcceptLanguageFromLanguageListOptOut 1
```

This cmdlet deletes the current content of the HTTP Accept Language registry key and blocks updates to the key based on changes to the user's language list.

## PARAMETERS

### -OptOut


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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WinAcceptLanguageFromLanguageListOptOut](./Get-WinAcceptLanguageFromLanguageListOptOut.md)

