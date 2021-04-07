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
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssremotewebaccessstatus?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssRemoteWebAccessStatus
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

