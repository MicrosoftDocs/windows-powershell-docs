---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/international/set-winlanguagebaroption?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WinLanguageBarOption
---

# Set-WinLanguageBarOption

## SYNOPSIS
Sets the language bar type and mode for the current user account.

## SYNTAX

```
Set-WinLanguageBarOption [-UseLegacySwitchMode] [-UseLegacyLanguageBar] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WinLanguageBarOption** cmdlet sets the language bar type and mode by using a LanguageBar object.
The values for the type and mode settings can be either true or false.
The default value for each setting is false.

## EXAMPLES

### Example 1
```
PS C:\>Set-WinLanguageBarOptions -UseLegacySwitchMode -UseLegacyLanguageBar
```

This command sets the language bar mode to the legacy setting and the language bar type to the per-thread setting.

### Example 2
```
PS C:\>Set-WinLanguageBarOptions
```

This command sets the language bar mode and the language bar type to the default setting.

## PARAMETERS

### -UseLegacyLanguageBar
When used with this cmdlet, this parameter sets the language bar mode to the legacy setting.
When this parameter is not used with the cmdlet, the language bar mode is set to the default setting.

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

### -UseLegacySwitchMode
When used with this cmdlet, this parameter sets the language bar switch mode to the legacy or per-thread setting.
When this parameter is not used with the cmdlet, the language bar switch mode is set to the default or per-user setting.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WinLanguageBarOption](./Get-WinLanguageBarOption.md)

