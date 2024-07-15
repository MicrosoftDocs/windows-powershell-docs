---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.WindowsSearch.Commands.dll-Help.xml
Module Name: WindowsSearch
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/windowssearch/get-windowssearchsetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WindowsSearchSetting
---

# Get-WindowsSearchSetting

## SYNOPSIS
Gets the values of settings for Windows Search.

## SYNTAX

```
Get-WindowsSearchSetting [<CommonParameters>]
```

## DESCRIPTION
The **Get-WindowsSearchSetting** cmdlet gets the values of settings for Windows Search.
You can view settings for whether Windows Search displays web results or suggestions and whether to display web results and suggestions while using a metered network.
You can view settings for whether Windows Search personalizes results, including whether Windows Search employs the specific location of the user.
You can also see SafeSearch settings.

## EXAMPLES

### Example 1: Get Windows Search settings
```
PS C:\> Get-WindowsSearchSetting
```

This command gets Windows Search settings.
The console displays the values for the settings.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### WindowsSearchSetting

Returns the values of properties that control Windows Search:

- EnableMeteredWebResultsSetting.
Whether Windows Search displays web results and suggestions while using a metered network.
- EnableWebResultsSetting.
Whether Windows Search displays web results and suggestions.
- SearchExperienceSetting.
The experience setting.
- WindowsSafeSearchSetting.
The value of SafeSearch that Windows Search uses for queries.

### SearchExperienceSetting

Has the following possible values:

- PersonalizedAndLocation.
Personalize Windows Search and other Microsoft experiences by using search history, some Microsoft account information, and specific location of the user.
- Personalized.
Personalize Windows Search and other Microsoft experiences by using search history and some Microsoft account information, but do not use specific location of the user.
- NotPersonalized.
Do not personalize Windows Search and other Microsoft experiences or use specific location of the user.

### WindowsSafeSearchSetting

Has the following possible values:

- Off.
Windows Search does not remove adult content from results.
- Moderate.
Windows Search excludes adult images and videos, but not text, from results.
- Strict.
Windows Search excludes adult images, videos, and text from results.

## NOTES

## RELATED LINKS

[Set-WindowsSearchSetting](./Set-WindowsSearchSetting.md)
