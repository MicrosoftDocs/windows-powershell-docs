---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssServerConnectionOption
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 8074EFD6-5235-46CA-97F9-3D63EE09AD6D
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssServerConnectionOption

## SYNOPSIS
Retrieves the server connection option.

## SYNTAX

```
Get-WssServerConnectionOption [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssServerConnectionOption** cmdlet retrieves the server connection option in sbs_sbs8_2.
WSS supports the use of a terminal session directly to the server (RemoteDesktop) or the use of the dashboard as a remote application (RemoteApp).

## EXAMPLES

### Example 1: Get the server connection option
```
PS C:\> Get-WssServerConnectionOption
```

This command gets the server connection option.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.String
This cmdlet generates a string object representing the server connection option, either RemoteDesktop or RemoteApp (Dashboard).

## NOTES

## RELATED LINKS

[Set-WssServerConnectionOption](./Set-WssServerConnectionOption.md)

