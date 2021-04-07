---
author: Kateyanne
description: 
external help file: WssCmdlets.dll-Help.xml
manager: jasgro
Module Name: WSSCmdlets
ms.author: v-kaunu
ms.date: 12/05/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssrouterinformation?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssRouterInformation
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

