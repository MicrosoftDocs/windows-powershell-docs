---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
online version: 
schema: 2.0.0
title: Set-Culture
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
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
For more information, see [CultureInfo Class](https://go.microsoft.com/fwlink/?LinkID=242306) and [Manage the input and display language settings in Windows 10](https://support.microsoft.com/help/4496404/windows-10-manage-the-input-and-display-language#input_language).

## EXAMPLES

### Example 1
```powershell
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
This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
Changes made by the use of this cmdlet will take effect on subsequent PowerShell sessions.
## RELATED LINKS

[GetCulture Class](https://go.microsoft.com/fwlink/?LinkID=243343)
