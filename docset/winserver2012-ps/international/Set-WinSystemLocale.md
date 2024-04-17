---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
online version: https://learn.microsoft.com/powershell/module/international/set-winsystemlocale?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-WinSystemLocale

## SYNOPSIS

Sets the system locale (the language for non-Unicode programs) for the current computer.

## SYNTAX

```powershell
Set-WinSystemLocale [-SystemLocale] <CultureInfo> [<CommonParameters>]
```

## DESCRIPTION

The **Set-WinSystemLocale** cmdlet sets the code pages (ANSI, DOS, and Macintosh) that the system uses by default.
If you change the system-locale setting, the necessary bitmap font files are installed to support legacy applications in the selected language.

Note that because this is a system setting, this can only be changed by a user with Administrator permissions, and changes do not take effect until the computer is restarted.

## EXAMPLES

### Example 1: Set the system locale

```powershell
PS C:\> Set-WinSystemLocale -SystemLocale ja-JP
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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### CultureInfo

An object that contains a BCP-47 tag to specify the system locale for the current computer.
For more information about the CultureInfo object, see [CultureInfo Class](https://go.microsoft.com/fwlink/?LinkID=242306).

## OUTPUTS

## NOTES
Please note that the System Locale setting on the computer is primarily used for legacy code page selection and font fallback. This setting is primarily used by applications that do not support Unicode. It should not be viewed from the sense of a traditional locale or culture info, and should not be confused with the user locale (Regional Format) setting.

When changing the System Locale setting it is highly recommended to also change the Windows Display Language or UI language setting for the computer so that it matches the System Locale. In some cases, the UI language may depend on the code page and/or the font to render properly. Failure to do so can result in configurations where non-Unicode applications don't work as intended.

## RELATED LINKS

[Manage the input and display language settings in Windows 10](https://support.microsoft.com/help/4496404/windows-10-manage-the-input-and-display-language#input_language)

