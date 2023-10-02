---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/international/set-winuserlanguagelist?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WinUserLanguageList
---

# Set-WinUserLanguageList

## SYNOPSIS
Sets the language list and associated properties for the current user account.

## SYNTAX

```
Set-WinUserLanguageList
 [-LanguageList] <System.Collections.Generic.List`1[Microsoft.InternationalSettings.Commands.WinUserLanguage]>
 [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WinUserLanguageList** cmdlet sets the current user language settings.
These settings include input method, spelling setting, text prediction setting, and handwriting input mode.
For more information, see [CultureInfo Class](https://go.microsoft.com/fwlink/?LinkID=242306) and [Manage the input and display language settings in Windows 10](https://support.microsoft.com/help/4496404/windows-10-manage-the-input-and-display-language#input_language).

## EXAMPLES

### Example 1
```
PS C:\> $OldList = Get-WinUserLanguageList
PS C:\> $OldList.Add("fr-FR")
PS C:\> Set-WinUserLanguageList $OldList
```

This command adds the language French (France) to the user's language list.

### Example 2
```
PS C:\>$1 = New-WinUserLanguageList en-US
PS C:\>$1[0].Handwriting = 1
PS C:\> Set-WinUserLanguageList $1
```

This command changes the handwriting setting for the language English (United States) in the user's language list to ON (write each character separately).

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force


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

### -LanguageList


```yaml
Type: System.Collections.Generic.List`1[Microsoft.InternationalSettings.Commands.WinUserLanguage]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Collections.Generic.List<Microsoft.InternationalSettings.Commands.WinUserLanguage>
A list of *WinUserLanguage* objects that contain one or more languages and associated properties from the current user account's language list. 
The language object contains the following properties:

--**BCP-47** (READ). A standard language tag that is used to identify languages. For more information, see the [Internet Engineering Task Force (IETF) BCP 47 RFC](https://go.microsoft.com/fwlink/?LinkID=242207).
--**Autonym** (LP database) (READ). The name of the language in the language itself.
--**English name** (LP database) (READ). The name of the language in English.
--**Localized name** (LP database) (READ). The name of the language in the current Windows display language.
--**Script** (LP database) (READ). The writing system of the language.
--**Input methods** (READ/WRITE). A list of input method Tablet Input Panel (TIP) strings that are enabled for this language. The enabled input methods are listed in the format `Language ID:Keyboard layout ID`. See [Default input profiles (input locales) in Windows](/windows-hardware/manufacture/desktop/default-input-locales-for-windows-language-packs).
--**Handwriting recognition input mode** (READ/WRITE). This value is either 0 (freehand) or 1 (write each character separately).

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WinUserLanguageList](./Get-WinUserLanguageList.md)

[New-WinUserLanguageList](./New-WinUserLanguageList.md)
