---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/international/set-culture?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Culture
---

# Set-Culture

## SYNOPSIS
Sets the user culture for the current user account.

## SYNTAX

```
Set-Culture [-CultureInfo] <CultureInfo> [<CommonParameters>]
```

## DESCRIPTION
The **Set-Culture** cmdlet sets a specific culture for the current user account.
A culture is known as a locale for unmanaged code development.
The information includes the names for the culture, the writing system, the calendar, and formatting for dates and sort strings.
For more information, see [CultureInfo Class](https://go.microsoft.com/fwlink/?LinkID=242306) and [Configurable Language and Cultural Settings](https://go.microsoft.com/fwlink/?LinkID=242307).

## EXAMPLES

### Example 1: Set the culture
```powershell
PS C:\> Set-Culture -CultureInfo de-DE
```

This command sets the culture for the current user account to German (Germany).

## PARAMETERS

### -CultureInfo
Specifies a culture.

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

