---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssReportHtml
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: C5A0EC96-CCD7-43E6-B09F-572B19888058
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssReportHtml

## SYNOPSIS
Gets the HTML string of a specific health report.

## SYNTAX

```
Get-WssReportHtml [-Id] <Guid> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssReportHtml** cmdlet gets the HTML string of a specific health report.

## EXAMPLES

### Example 1: Get the report HTML string
```
PS C:\> Get-WssReportHtml | Out-File -Filepath C:\Test01\Report.html
```

This command gets the report HTML string on the server on which you run the cmdlet.

### 1:
```
PS C:\>
```

## PARAMETERS

### -Id
Specifies the ID of a report instance.
The cmdlet gets the report instance for the ID that you specify.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Guid

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS

