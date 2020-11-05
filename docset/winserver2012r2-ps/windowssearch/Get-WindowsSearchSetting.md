---
external help file: Microsoft.WindowsSearch.Commands.dll-Help.xml
Module Name: WindowsSearch
online version: 
schema: 2.0.0
title: Get-WindowsSearchSetting
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 16F4C925-AD39-46EF-88B0-913988DDC35C
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WindowsSearchSetting

## SYNOPSIS
Gets the values of settings for Windows Search.

## SYNTAX

```
Get-WindowsSearchSetting [<CommonParameters>]
```

## DESCRIPTION
The **Get-WindowsSearchSettings** cmdlet gets the values of settings for Windows Search.
You can view settings for whether Windows Search displays web results or suggestions and whether to display web results and suggestions while using a metered network.
You can view settings for whether Windows Search personalizes results, including whether Windows Search employs  the specific location of the user.
You can also see SafeSearch settings.

## EXAMPLES

### Example 1: Get Windows Search settings
```
PS C:\> Get-WindowsSearchSetting
Setting                                                     Value
-------                                                     -----
EnableWebResultsSetting                                     True
EnableMeteredWebResultsSetting                              True
SearchExperience                                            PersonalizedAndLocation
WindowsSafeSearchSetting                                    Moderate
```

This command gets Windows Search settings.
The console displays the values for the settings.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### WindowsSearchSetting
Returns the values of properties that control Windows Search:

- **EnableMeteredWebResultsSetting**. Whether Windows Search displays web results and suggestions while using a metered network. 
- **EnableWebResultsSetting**. Whether Windows Search displays web results and suggestions. 
- **SearchExperienceSetting**. The experience setting. 
- **WindowsSafeSearchSetting**. The value of SafeSearch that Windows Search uses for queries.

**SearchExperienceSetting** has the following possible values: 

- PersonalizedAndLocation.
Personalize Windows Search and other Microsoft experiences by using search history, some Microsoft account information, and specific location of the user. 
- Personalized.
Personalize Windows Search and other Microsoft experiences by using search history and some Microsoft account information, but do not use specific location of the user. 
- NotPersonalized.
Do not personalize Windows Search and other Microsoft experiences or use specific location of the user.

**WindowsSafeSearchSetting** has the following possible values: 

- Off.
Windows Search does not remove adult content from results.
- Moderate.
Windows Search excludes adult images and videos, but not text, from results.
- Strict.
Windows Search excludes adult images, videos, and text from results.

## NOTES

## RELATED LINKS

[Set-WindowsSearchSetting](./Set-WindowsSearchSetting.md)

