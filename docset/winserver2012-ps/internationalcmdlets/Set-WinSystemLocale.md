---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
ms.assetid: FD1D3195-FDB1-48AE-A76E-FD9A2B164925
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Set-WinSystemLocale

## SYNOPSIS
Sets the system locale (the language for non-Unicode programs) for the current computer.

## SYNTAX

```
Set-WinSystemLocale [-SystemLocale] <CultureInfo> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WinSystemLocale** cmdlet sets the code pages (ANSI, DOS, and Macintosh) that the system uses by default.
If you change the system-locale setting, the necessary bitmap font files are installed to support legacy applications in the selected language.
Note that because this is a system setting, this can only be changed by a user with Administrator permissions, and changes do not take effect until the computer is restarted.

## EXAMPLES

### Example 1: Set the system locale
```
PS C:\>Set-WinSystemLocale -SystemLocale ja-JP
```

This command sets the system locale to Japanese (Japan).

## PARAMETERS

### -SystemLocale
Specifies the system locale.

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

