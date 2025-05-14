---
description: The Get-InstalledLanguage cmdlet lets you see which languages are installed in a running Windows installation
external help file: Microsoft.LanguagePackManagement.Powershell.Commands.dll-Help.xml
Module Name: LanguagePackManagement
ms.date: 08/15/2022
online version: https://learn.microsoft.com/powershell/module/languagepackmanagement/get-installedlanguage?view=windowsserver2025-ps
schema: 2.0.0
title: Get-InstalledLanguage
---

# Get-InstalledLanguage

## SYNOPSIS
Returns information about the installed languages on a device.

## SYNTAX

```
Get-InstalledLanguage [-Language] <String> [<CommonParameters>]
```

## DESCRIPTION
Returns a list of the installed languages and related Language features installed on the device.

## EXAMPLES

### Example 1: See what languages are installed on a device

```powershell
Get-InstalledLanguage
```

This command will show all of the language components that are installed on a device.

### Example 2: See which language components are installed for a particular language

```powershell
Get-InstalledLanguage -language en-US
```

This command will show the language features that are installed for the en-US language.

## PARAMETERS

### -Language

Shows the language components that are installed for the specified language.

```yaml
Type: String
Parameter Sets: (All)
Aliases: LanguageId, LanguageTag

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Collections.Generic.List<Microsoft.LanguagePackManagement.Powershell.Commands.InstalledLanguage>

## NOTES

## RELATED LINKS

[Set-SystemPreferredUILanguage](Set-SystemPreferredUILanguage.md)
