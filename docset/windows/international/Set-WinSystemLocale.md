---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-WinSystemLocale
ms.reviewer:
ms.assetid: 1A63BE0A-9B09-4302-B0BE-74CB7A799D18
---

# Set-WinSystemLocale

## SYNOPSIS
Sets the system locale for the current computer.

## SYNTAX

```
Set-WinSystemLocale [-SystemLocale] <CultureInfo> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WinSystemLocale** cmdlet sets the system locale for the current computer.
The System-locale setting determines which code pages, which include ANSI, DOS, and Macintosh, the computer uses by default.
If you change the System-locale setting, the necessary bitmap font files are installed to support legacy applications in the selected language.

This is a system setting.
It can only be changed by a user who has Administrator permissions.
Changes take effect after the computer is restarted.

## EXAMPLES

### Example 1: Set the system locale
```
PS C:\> Set-WinSystemLocale -SystemLocale ja-JP
```

This command sets the system locale to Japanese (Japan).

## PARAMETERS

### -SystemLocale
Specifies a system locale.

```yaml
Type: CultureInfo
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### CultureInfo
An object that contains a BCP-47 tag to specify the system locale for the current computer.
For more information about the CultureInfo object, see [CultureInfo Class](http://go.microsoft.com/fwlink/?LinkID=242306).

## OUTPUTS

## NOTES

## RELATED LINKS

[Manage the input and display language settings in Windows 10](https://support.microsoft.com/en-us/help/4496404/windows-10-manage-the-input-and-display-language#input_language)

[Get-WinSystemLocale](./Get-WinSystemLocale.md)

