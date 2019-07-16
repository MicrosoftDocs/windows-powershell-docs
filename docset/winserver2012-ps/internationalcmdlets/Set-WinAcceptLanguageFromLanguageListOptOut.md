---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
ms.assetid: EA54CF2E-14C7-47C2-9DD9-8D495A08222F
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Set-WinAcceptLanguageFromLanguageListOptOut

## SYNOPSIS
Sets the HTTP Accept Language from the Language List opt-out setting for the current user account.

## SYNTAX

```
Set-WinAcceptLanguageFromLanguageListOptOut [-OptOut] <Boolean> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WinAcceptLanguageFromLanguageListOptOut** cmdlet sets the HTTP Accept Language from the Language List opt-out setting for the current user account.
By default, the HTTP Accept Language List is automatically generated from the current user account's language list.
You can use the **Set-WinAcceptLanguageFromLanguageListOptOut** cmdlet to set the **HTTP Accept Language from Language List opt-out** value.
When set to $True, this setting deletes the current content of the HTTP Accept Language registry key and prevents changes to the language list from reestablishing the key.
When set to $False, this setting reestablishes the HTTP Accept Language List based on the language list for the current user account.

## EXAMPLES

### Example 1: Set the HTTP Accept Language registry key
```
PS C:\> Set-WinAcceptLanguageFromLanguageListOptOut -OptOut 1
```

This cmdlet deletes the current content of the HTTP Accept Language registry key and blocks updates to the key based on changes to the user's language list.

## PARAMETERS

### -OptOut
Indicates whether to opt out from the Language List.

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

