---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssReportSection
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-12-05
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 7C50DE04-27FB-4A42-9DBE-F1CB949658C2
ms.manager: dansimp
ms.author: kenwith
ms.reviewer: brianlic
---

# Get-WssReportSection

## SYNOPSIS
Gets a listing of the sections to include in a health report.

## SYNTAX

```
Get-WssReportSection [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssReportSection** cmdlet gets a listing of the sections to include in a health report.
The sections include: 

- Backups 
- CriticalAlertsAndWarnings 
- ErrorsInEventLog 
- SecurityAndUpdates 
- ServiceNotRunning 
- Storage

## EXAMPLES

### Example 1: Get the report sections
```
PS C:\> Get-WssReportSection
```

This command gets the report sections for a health report on the server on which you run the cmdlet.

### 1:
```
PS C:\>
```

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.Administration.WssReportSection

## NOTES

## RELATED LINKS

[Set-WssReportSection](./Set-WssReportSection.md)

