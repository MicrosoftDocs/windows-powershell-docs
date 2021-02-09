---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
ms.assetid: FAF0A6E7-0F79-441E-B4D5-AEE8C1993ECE
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
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

### Example 1: Set the culture for the current user
```
PS C:\>Set-Culture -CultureInfo de-DE
```

This command sets the culture for the current user account to German (Germany).

## PARAMETERS

### -CultureInfo
Specifies the culture.

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

[GetCulture Class](https://go.microsoft.com/fwlink/?LinkID=243343)
