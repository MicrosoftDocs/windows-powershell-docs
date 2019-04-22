---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
ms.assetid: F8C3B107-1E88-445D-8C51-D9EAED20A0C2
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Set-WinDefaultInputMethodOverride

## SYNOPSIS
Sets the default input method override for the current user account.

## SYNTAX

```
Set-WinDefaultInputMethodOverride [[-InputTip] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WinDefaultInputMethodOverride** cmdlet gets the default input method override setting, which specifies a default input method for the current user account.
If no override setting is used, the input method is dynamically determined from the current user account's language list (see Get-WinUserLanguageList and Set-WinUserLanguageList).

## EXAMPLES

### Example 1: Set the default input method override
```
PS C:\>Set-WinDefaultInputMethodOverride -InputTip "0409:00000409"
```

This command sets the default input method override to English (United States) - US.

## PARAMETERS

### -InputTip
Specifies a locale ID and a keyboard language ID (KLID).

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### InputTip
A string that consists of a locale ID and a keyboard language ID (KLID).

## OUTPUTS

## NOTES

## RELATED LINKS

