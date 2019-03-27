---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssRemoteWebAccessLink
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-12-05
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 3DDFCA4C-CF8C-4BBB-83C7-BD6BC1A9A2B8
ms.author: kenwith
ms.reviewer: brianlic
---

# Get-WssRemoteWebAccessLink

## SYNOPSIS
Retrieves the collection of links on the home page of a Remote Web Access website

## SYNTAX

```
Get-WssRemoteWebAccessLink [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssRemoteWebAccessLink** cmdlet retrieves the collection of links on the home page of a Remote Web Access website.
The links are key-value pairs of IDs and link items.

To remove a link from the home page of a Remote Web Access website, use the **Remove-WssRemoteWebAccessLink** cmdlet.

## EXAMPLES

### Example 1: Retrieve a collection of links
```
PS C:\> Get-WssRemoteWebAccessLink
```

This command retrieves the collection of links on the home page of a Remote Web Access website.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Collections.Generic.Dictionary<System.String, Microsoft.WindowsServerSolutions.Web.Admin.RemoteAccessLinkItem>
This cmdlet generates a dictionary object where each value represents a link in Remote Web Access.

## NOTES

## RELATED LINKS

[Add-WssRemoteWebAccessLink](./Add-WssRemoteWebAccessLink.md)

[Remove-WssRemoteWebAccessLink](./Remove-WssRemoteWebAccessLink.md)

