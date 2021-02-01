---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssRemoteWebAccessBackgroundImage
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 98F5EC0F-5604-4ECB-B88B-62942BA5D949
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssRemoteWebAccessBackgroundImage

## SYNOPSIS
Retrieves the filename of the background image displayed on the Remote Web Access website.

## SYNTAX

```
Get-WssRemoteWebAccessBackgroundImage [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssRemoteWebAccessBackgroundImage** cmdlet retrieves the filename of the background image displayed on the logon page of the Remote Web Access website.

## EXAMPLES

### Example 1: Retrieve the filename of the background image
```
PS C:\> Get-WssRemoteWebAccessLink
```

This command retrieves the filename of the background image.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.String
This cmdlet generates a string object that represents the filename of a customized background image.
The cmdlet does not generate any output if Remote Web Access uses the default image.

## NOTES

## RELATED LINKS

[Set-WssRemoteWebAccessBackgroundImage](./Set-WssRemoteWebAccessBackgroundImage.md)

