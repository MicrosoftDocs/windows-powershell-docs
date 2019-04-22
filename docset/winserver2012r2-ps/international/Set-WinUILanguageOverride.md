---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
online version: 
schema: 2.0.0
title: Set-WinUILanguageOverride
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
ms.assetid: ADFB5B71-666D-40AB-9F9C-8F0E3EC0F421
---

# Set-WinUILanguageOverride

## SYNOPSIS
Sets the Windows user interface (UI) language override setting for the current user account.

## SYNTAX

```
Set-WinUILanguageOverride [[-Language] <CultureInfo>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WINUILanguageOverride** cmdlet sets a user-preferred display language to be used for the Windows UI.
If no override setting is used, the display language is dynamically determined from the user's language list (see Get-WinUserLanguageList and Set-WinUserLanguageList).

## EXAMPLES

### Example 1
```
PS C:\>Set-WinUILanguageOverride de-DE
```

This command sets the Windows UI language override to German (Germany) for the current user account.

### Example 2
```
PS C:\>Set-WinUILanguageOverride
```

This command sets the Windows UI language override to null for the current user account.

## PARAMETERS

### -Language


```yaml
Type: CultureInfo
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### CultureInfo
An object that contains the Windows UI language override for the current user account.
For more information about the CultureInfo object, see CultureInfo Classhttp://go.microsoft.com/fwlink/?LinkID=242306.

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WinUILanguageOverride](./Get-WinUILanguageOverride.md)

