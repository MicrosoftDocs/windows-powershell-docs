---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssBranchCacheStatus
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: DA388B1B-E097-413F-B87C-3AA6B90B6A35
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssBranchCacheStatus

## SYNOPSIS
Gets the current BranchCache status.

## SYNTAX

```
Get-WssBranchCacheStatus [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssBranchCacheStatus** cmdlet gets the current BranchCache service status on the target computer, either enabled or disabled.
BranchCache copies content from on-premise content servers or hosted cloud content servers and caches the content at branch office locations.

## EXAMPLES

### Example 1: Get BranchCache status
```
PS C:\> Get-WssBranchCacheStatus
```

This command gets the status of BranchCache on the server where you run the cmdlet.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.BranchCache.BranchCacheStatus

## NOTES

## RELATED LINKS

