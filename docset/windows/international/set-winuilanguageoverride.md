---
author: brianlic
description: 
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-WinUILanguageOverride
ms.assetid: ADFB5B71-666D-40AB-9F9C-8F0E3EC0F421
---

# Set-WinUILanguageOverride

## SYNOPSIS
Sets the Windows UI language override setting for the current user account.

## SYNTAX

```
Set-WinUILanguageOverride [[-Language] <CultureInfo>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WinUILanguageOverride** cmdlet sets a user-preferred display language to be used for the Windows user interface (UI).
If no override setting is used, the display language is dynamically determined from the language list of the user.
For more information, see the Get-WinUserLanguageList and Set-WinUserLanguageList cmdlets.

## EXAMPLES

### Example 1: Set a language override
```
PS C:\>Set-WinUILanguageOverride -Language de-DE
```

This command sets the Windows UI language override to German (Germany) for the current user account.

### Example 2: Set a language override to null
```
PS C:\>Set-WinUILanguageOverride
```

This command sets the Windows UI language override to null for the current user account.

## PARAMETERS

### -Language
Specifies a language.

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
You can pipe an object that contains the Windows UI language override for the current user account.
For more information about the **CultureInfo** object, see CultureInfo Classhttp://go.microsoft.com/fwlink/?LinkID=242306.

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WinUILanguageOverride](./Get-WinUILanguageOverride.md)

[Get-WinUserLanguageList](./Get-WinUserLanguageList.md)

[Set-WinUserLanguageList](./Set-WinUserLanguageList.md)

