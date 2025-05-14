---
description: The Set-SystemPreferredUILanguage cmdlet lets you set an installed language as the System Preferred UI Language in a running Windows installation
external help file: Microsoft.LanguagePackManagement.Powershell.Commands.dll-Help.xml
Module Name: LanguagePackManagement
ms.date: 08/15/2022
online version: https://learn.microsoft.com/powershell/module/languagepackmanagement/set-systempreferreduilanguage?view=windowsserver2025-ps
schema: 2.0.0
title: Set-SystemPreferredUILanguage
---

# Set-SystemPreferredUILanguage

## SYNOPSIS
Sets the provided language as the System Preferred UI Language.

## SYNTAX

```
Set-SystemPreferredUILanguage [-Language] <String> [-PassThru] [<CommonParameters>]
```

## DESCRIPTION

Sets the provided language as the System Preferred UI Language.

After a language is set as the System Preferred UI Language, you have to restart the device or login again for changes to take effect. Additional accounts created after setting the System Preferred UI Langauge will be configured to use the new language.

## EXAMPLES

### Example 1: Set the System Preferred UI Language on a Windows installation

```powershell
Set-SystemPreferredUILanguage ja-JP
```

This command sets the System Preferred UI Language to Japanese.

## PARAMETERS

### -Language

The bcp47 tag of the language to set as the System Preferred UI Language.

```yaml
Type: String
Parameter Sets: (All)
Aliases: LanguageId, LanguageTag

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru

If specified, this parameter returns the bcp47 tag of the language upon successful configuration of the System Preferred UI Language.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Void

### System.String

## NOTES

## RELATED LINKS

[Get-SystemPreferredUILanguage](Set-SystemPreferredUILanguage.md)
