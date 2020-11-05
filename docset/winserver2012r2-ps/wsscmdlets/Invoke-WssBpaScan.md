---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Invoke-WssBpaScan
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 37789768-AEF7-4B6A-852D-4E957DC3A423
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Invoke-WssBpaScan

## SYNOPSIS
Starts a BPA scan.

## SYNTAX

```
Invoke-WssBpaScan [<CommonParameters>]
```

## DESCRIPTION
The **Invoke-WssBpaScan** cmdlet starts a Best Practices Analyzer (BPA) scan that raises BPA error or warning alerts.
The BPA compares the server configuration with guidelines for the ideal way, under normal circumstances, to configure a server.

## EXAMPLES

### Example 1: Start a BPA scan
```
PS C:\> Invoke-WssBpaScan
```

This command starts a BPA scan.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssBpaScanResult](./Get-WssBpaScanResult.md)

