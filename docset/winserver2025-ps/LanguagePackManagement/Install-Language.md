---
description: The Install-Language cmdlet lets you add a language to a running Windows installation
external help file: Microsoft.LanguagePackManagement.Powershell.Commands.dll-Help.xml
Module Name: LanguagePackManagement
ms.date: 08/15/2022
online version: https://learn.microsoft.com/powershell/module/languagepackmanagement/install-language?view=windowsserver2025-ps
schema: 2.0.0
title: Install-Language
---

# Install-Language

## SYNOPSIS
Installs a language onto a device.

## SYNTAX

```
Install-Language [-Language] <String> [-CopyToSettings] [-ExcludeFeatures] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

Downloads and installs the available language components for the specified language onto a device.

You can also change your Display Language by using the International module commands (`Set-WinUILanguageOverride <lnstalled Language>`)

## EXAMPLES

### Example 1: Add a language to a device

```powershell
Install-Language ja-JP
```

This command adds the Japanese language to a device.

## PARAMETERS

### -AsJob

If specified, this parameter will execute the language installation as an [async PowerShell job](/powershell/module/microsoft.powershell.core/about/about_jobs).

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

### -CopyToSettings

If specified, this parameter sets the System and Default Device Settings (Windows Display Language, regional and locale formats) to the installed language following the installation.

After a language is added with this command, you have to restart the device or login again for changes to take effect. Once you log back in, you can change your Windows Display Language in  Settings App to change the device UI language.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: ApplyToSettings, ApplyToInternationalSettings, CopyToInternationalSettings

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludeFeatures

If specified, the associated language Features on Demand won't be installed.

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

### -Language

The bcp47 tag of the language that you're installing.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.LanguagePackManagement.Powershell.Commands.InstallLanguage+InstallLanguageJob

### System.Collections.Generic.List<Microsoft.LanguagePackManagement.Powershell.Commands.InstalledLanguage>

## RELATED LINKS

[UninstallLanguage](uninstall-language.md)
