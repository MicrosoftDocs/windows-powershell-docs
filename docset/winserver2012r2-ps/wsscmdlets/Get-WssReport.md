---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssReport
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 68A11550-85A7-4311-88CA-35984A504B5C
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssReport

## SYNOPSIS
Gets the full list of unexpired health reports.

## SYNTAX

```
Get-WssReport [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssReport** cmdlet gets the full list of unexpired health reports, including manually-generated and auto-generated reports.

## EXAMPLES

### Example 1: Get all health reports
```
PS C:\> Get-WssReport
```

This command gets all health reports on the server where you run the cmdlet.

### 1:
```
PS C:\>
```

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.Administration.WssReport

## NOTES

## RELATED LINKS

[New-WssReport](./New-WssReport.md)

[Remove-WssReport](./Remove-WssReport.md)

[Send-WssReport](./Send-WssReport.md)

