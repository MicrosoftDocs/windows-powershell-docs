---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
online version: https://docs.microsoft.com/powershell/module/international/get-winculturefromlanguagelistoptout?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WinCultureFromLanguageListOptOut

## SYNOPSIS
Gets the Culture (User Locale) from the language list opt-out setting for the current user account.

## SYNTAX

```
Get-WinCultureFromLanguageListOptOut [<CommonParameters>]
```

## DESCRIPTION
The **Get-WinCultureFromLanguageListOptOut** cmdlet gets the Culture (User Locale) override setting for the current user account.
When set to $True, the Culture setting is not updated by changes to the Windows display language.
When set the $False, the Culture setting can be reassigned to match the display language changes any time that the display language changes.
The default setting is $False.

## EXAMPLES

### Example 1: Get the Culture (User Locale) for the current user
```
PS C:\>Get-WinCultureFromLanguageListOptOut
```

This command gets the Culture (User Locale) for the current user.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Boolean
A Boolean value that reports the status of this setting.

## NOTES

## RELATED LINKS

