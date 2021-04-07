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
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssreportsection?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssReportSection
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

