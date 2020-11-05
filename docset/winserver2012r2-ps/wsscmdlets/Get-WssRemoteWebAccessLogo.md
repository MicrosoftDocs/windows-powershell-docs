---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssRemoteWebAccessLogo
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 7DBE5E22-F552-401B-96E2-DB0E40EAFCB8
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssRemoteWebAccessLogo

## SYNOPSIS
Retrieves the name of the file that contains the logo for the Remote Web Access website.

## SYNTAX

```
Get-WssRemoteWebAccessLogo [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssRemoteWebAccessLogo** cmdlet retrieves the name of the file that contains the logo for the Remote Web Access website in sbs_sbs8_2.
The logo image customizes the appearance of the Remote Web Access website.

## EXAMPLES

### Example 1: Retrieve the name of the logo file
```
PS C:\> Get-WssRemoteWebAccessLogo
```

This command retrieves the name of the file that contains the logo for the Remote Web Access website.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.String
This cmdlet generates a string object that represents the filename of customized logo.
The cmdlet does not generate any output if Remote Web Access uses the default logo.

## NOTES

## RELATED LINKS

[Set-WssRemoteWebAccessLogo](./Set-WssRemoteWebAccessLogo.md)

