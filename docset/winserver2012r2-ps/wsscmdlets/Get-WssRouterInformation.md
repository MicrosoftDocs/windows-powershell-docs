---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssRouterInformation
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 962FE350-3511-4377-9689-FF55DACA7BA4
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssRouterInformation

## SYNOPSIS
Retrieves information about the router for the local network.

## SYNTAX

```
Get-WssRouterInformation [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssRouterInformation** cmdlet retrieves information about the router, including the IP address, name, and model.

If the router supports Universal Plug and Play (UPnP), sbs_sbs8_2 server may be able to configure the router for your local network.
If the router does not support UPnP, you must manually configure the router.

## EXAMPLES

### Example 1: Retrieve router information
```
PS C:\> Get-WssRouterInformation
```

This command retrieves the router information for the local network.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

