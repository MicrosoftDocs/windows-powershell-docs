---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
online version: https://learn.microsoft.com/powershell/module/international/set-winculturefromlanguagelistoptout?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-WinCultureFromLanguageListOptOut

## SYNOPSIS
Sets the Culture (User Locale) from language list opt-out setting for the current user account.

## SYNTAX

```
Set-WinCultureFromLanguageListOptOut [-OptOut] <Boolean> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WinCultureFromLanguageListOptOut** cmdlet sets the Culture (User Locale) opt-out setting for the current user account.
Setting this option to $True disables the action of dynamically setting the Culture (User Locale) for the current user based on changes to the Windows display language.
Setting this option to $False activates the dynamic setting behavior.
The default setting is $False.

## EXAMPLES

### Example 1: Opt out of the culture from language list behavior
```
PS C:\>Set-WinCultureFromLanguageListOptOut -OptOut $True
```

This cmdlet blocks the dynamic setting behavior.

## PARAMETERS

### -OptOut
Indicates whether to opt out of the culture from language list behavior.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

