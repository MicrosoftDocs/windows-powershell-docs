---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
Module Name: International
online version: https://docs.microsoft.com/powershell/module/international/set-winuilanguageoverride?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-WinUILanguageOverride

## SYNOPSIS
Sets the Windows UI language override setting for the current user account.

## SYNTAX

```
Set-WinUILanguageOverride [[-Language] <CultureInfo>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WINUILanguageOverride** cmdlet sets a user-preferred display language to use for the Windows user interface (UI).
If no override setting is specified, the display language is dynamically determined from the user's language list (see Get-WinUserLanguageList and Set-WinUserLanguageList).

## EXAMPLES

### Example 1: Set the Windows UI language override
```
PS C:\>Set-WinUILanguageOverride -Language de-DE
```

This command sets the Windows UI language override to German (Germany) for the current user account.

### Example 2: Set the Windows UI language override to $Null
```
PS C:\>Set-WinUILanguageOverride
```

This command sets the Windows UI language override to $Null for the current user account.

## PARAMETERS

### -Language
Specifies a **CultureInfo** object.

```yaml
Type: CultureInfo
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### CultureInfo
An object that contains the Windows UI language override for the current user account.
For more information about the CultureInfo object, see CultureInfo Classhttps://go.microsoft.com/fwlink/?LinkID=242306.

## OUTPUTS

## NOTES

## RELATED LINKS

