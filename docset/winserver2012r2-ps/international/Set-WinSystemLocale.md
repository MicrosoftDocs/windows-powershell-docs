---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
online version: 
schema: 2.0.0
title: Set-WinSystemLocale
ms.author: kenwith
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 1A63BE0A-9B09-4302-B0BE-74CB7A799D18
---

# Set-WinSystemLocale

## SYNOPSIS
Sets the system locale (the language for non-Unicode programs) for the current computer.

## SYNTAX

```
Set-WinSystemLocale [-SystemLocale] <CultureInfo> [<CommonParameters>]
```

## DESCRIPTION
The System-locale setting determines which code pages (ANSI, DOS, and Macintosh) the system uses by default.
If you change the System-locale setting, the necessary bitmap font files are installed to support legacy applications in the selected language.
Note that because this is a system setting, this can only be changed by a user with Administrator permissions, and changes do not take effect until the computer is restarted.

## EXAMPLES

### Example 1
```
PS C:\>Set-WinSystemLocale ja-JP
```

This command sets the system locale to Japanese (Japan).

## PARAMETERS

### -SystemLocale

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### CultureInfo
An object that contains a BCP-47 tag to specify the system locale for the current computer.
For more information about the CultureInfo object, see CultureInfo Classhttp://go.microsoft.com/fwlink/?LinkID=242306.

## OUTPUTS

## NOTES

## RELATED LINKS

[Configurable Language and Cultural Settings](http://go.microsoft.com/fwlink/?LinkID=242307)

[Get-WinSystemLocale](./Get-WinSystemLocale.md)
