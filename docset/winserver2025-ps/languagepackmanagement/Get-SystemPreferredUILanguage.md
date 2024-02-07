---
description: The Get-SystemPreferredUILanguage cmdlet lets you see which language is set as the System Preferred UI Language in a running Windows installation
external help file: Microsoft.LanguagePackManagement.Powershell.Commands.dll-Help.xml
Module Name: LanguagePackManagement
ms.date: 06/21/2023
online version: https://learn.microsoft.com/powershell/module/languagepackmanagement/get-systempreferreduilanguage?view=windowsserver2022-ps
schema: 2.0.0
title: Get-SystemPreferredUILanguage
---

# Get-SystemPreferredUILanguage

## SYNOPSIS
Returns the current System Preferred Language.

## SYNTAX

```
Get-SystemPreferredUILanguage [<CommonParameters>]
```

## DESCRIPTION

Returns the language that is set as the System Preferred Language

## EXAMPLES

### Example 1

```powershell
Get-SystemPreferredUILanguage
```

This command returns the language that's currently set as the System Preferred UI Language

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.String

## RELATED LINKS

[Set-SystemPreferredUILanguage](set-systempreferreduilanguage.md)
[InstallLanguage](install-language.md)
