---
external help file: Microsoft.InternationalSettings.Commands.dll-Help.xml
ms.assetid: 0DCB2B97-03B9-4250-9A22-DEB34949136D
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-WinAcceptLanguageFromLanguageListOptOut

## SYNOPSIS
Gets the HTTP Accept Language from the Language List opt-out setting for the current user account.

## SYNTAX

```
Get-WinAcceptLanguageFromLanguageListOptOut [<CommonParameters>]
```

## DESCRIPTION
The **Get-WinAcceptLanguageFromLanguageListOptOut** cmdlet gets the **HTTP Accept Language from Language List opt-out** setting for the current user account.
By default, the **HTTP Accept Language List** is automatically generated from the current user account's language list.

When set to $True, this setting deletes the current content of the HTTP Accept Language registry key and prevents changes to the language list from reestablishing the key.
When set to $False, this setting reestablishes the **HTTP Accept Language List** that is based on the language list for the current user account.

## EXAMPLES

### Example 1: Get the HTTP Accept Language from Language List opt-out setting
```
PS C:\>Get-WinAcceptLanguageFromLanguageListOptOut
TRUE
```

This command returns the status of the **HTTP Accept Language from Language List opt-out** setting for the current user account.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Boolean
A Boolean value that reports the status of the **HTTP Accept Language from Language List opt-out** setting for the current user account.

## NOTES

## RELATED LINKS

