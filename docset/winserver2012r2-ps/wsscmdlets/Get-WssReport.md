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
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssreport?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssReport
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

