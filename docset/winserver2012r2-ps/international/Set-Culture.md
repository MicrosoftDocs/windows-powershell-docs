---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
online version: 
schema: 2.0.0
title: Set-Culture
description: 
keywords: powershell, cmdlet
author: brianlic
manager: alanth
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: D46BF01E-B43B-49DD-89EB-388C8F3CCB41
---

# Set-Culture

## SYNOPSIS
Sets the user culture for the current user account.

## SYNTAX

```
Set-Culture [-CultureInfo] <CultureInfo> [<CommonParameters>]
```

## DESCRIPTION
The **Set-Culture** cmdlet sets a specific culture (also known as a locale for unmanaged code development) for the current user account.
The information includes the names for the culture, the writing system, the calendar, and formatting for dates and sort strings.
For more information, see CultureInfo Classhttp://go.microsoft.com/fwlink/?LinkID=242306 and Configurable Language and Cultural Settingshttp://go.microsoft.com/fwlink/?LinkID=242307.

## EXAMPLES

### Example 1
```
PS C:\>Set-Culture de-DE
```

This command sets the culture for the current user account to German (Germany).

## PARAMETERS

### -CultureInfo


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

## OUTPUTS

## NOTES

## RELATED LINKS

[GetCulture Class](http://go.microsoft.com/fwlink/?LinkID=243343)

