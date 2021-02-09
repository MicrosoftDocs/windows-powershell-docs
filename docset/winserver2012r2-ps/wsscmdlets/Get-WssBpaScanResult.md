---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssBpaScanResult
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 8892B5A9-10A4-4918-8602-8187526ACA7F
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssBpaScanResult

## SYNOPSIS
Gets the most recent BPA scan result.

## SYNTAX

```
Get-WssBpaScanResult [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssBpaScanResult** cmdlet gets the most recent Best Practices Analyzer (BPA) scan result.
The BPA compares the server configuration with guidelines for the ideal way, under normal circumstances, to configure a server.

## EXAMPLES

### Example 1: Get a BPA scan result
```
PS C:\> Get-WssBpaScanResult
```

This command gets the most recent BPA scan result.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.BPA.WssBpaIssue
This cmdlet returns BPA issues.

## NOTES

## RELATED LINKS

[Invoke-WssBpaScan](./Invoke-WssBpaScan.md)

