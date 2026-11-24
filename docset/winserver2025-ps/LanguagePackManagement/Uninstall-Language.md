---
description: The Uninstall-Language cmdlet lets you remove a language and its components from a running Windows installation
external help file: Microsoft.LanguagePackManagement.Powershell.Commands.dll-Help.xml
Module Name: LanguagePackManagement
ms.date: 08/15/2022
online version: https://learn.microsoft.com/powershell/module/languagepackmanagement/uninstall-language?view=windowsserver2025-ps
schema: 2.0.0
title: Uninstall-Language
---

# Uninstall-Language

## SYNOPSIS
Uninstalls a language from a device.

## SYNTAX

```
Uninstall-Language [-Language] <String> [-PassThru] [<CommonParameters>]
```

## DESCRIPTION

Uninstalls a language, including all language components, from a device. This operation runs asynchronously.

## EXAMPLES

### Example 1: Remove a language from a device

```powershell
Uninstall-Language ja-jp
```

This command removes the Japanese language from the device.

## PARAMETERS

### -Language

The bcp47 tag of the language to install.

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

If specified, this parameter returns the bcp47 tag of the newly installed language upon successful installation.

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

[InstallLanguage](Install-Language.md)
