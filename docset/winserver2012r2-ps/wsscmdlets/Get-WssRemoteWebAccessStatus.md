---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssRemoteWebAccessStatus
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 9CE1E093-BC06-4F23-8ECE-535C443DC0A3
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssRemoteWebAccessStatus

## SYNOPSIS
Retrieves the status of a Remote Web Access website.

## SYNTAX

```
Get-WssRemoteWebAccessStatus [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssRemoteWebAccessStatus** cmdlet retrieves the status of a Remote Web Access website in sbs_sbs8_2.
The status information includes the status of the website and the state of the router and the domain.

## EXAMPLES

### Example 1: Retrieve the status of the website
```
PS C:\> Get-WssRemoteWebAccessStatus
```

This command retrieves the status of the Remote Web Access website.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsServerSolutions.Admin.RemoteAccess.RemoteAccessStatus
This cmdlet generates a remote access status object that represents the status of Remote Web Access.

## OUTPUTS

## NOTES

## RELATED LINKS

