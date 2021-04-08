---
author: Kateyanne
external help file: WSS_Cmdlets.xml
manager: dansimp
Module Name: WssCmdlets
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssrouterinformation?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WssRouterInformation

## SYNOPSIS
Retrieves information about the router for the local network.

## SYNTAX

```
Get-WssRouterInformation
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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS



