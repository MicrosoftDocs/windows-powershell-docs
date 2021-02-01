---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Set-WssReportSection
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 613B028A-60E9-49B4-BE33-283BFCA4087E
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Set-WssReportSection

## SYNOPSIS
Sets the sections to include in a health report.

## SYNTAX

```
Set-WssReportSection [-Section] <WssReportSection> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssReportSection** cmdlet sets the sections to include in a health report.

## EXAMPLES

### Example 1: Set the report sections for a health report
```
PS C:\> Set-WssReportSection ShowCriticalAlertsAndWarnings,ShowBackups
```

This command sets the report sections for a health report on a server where you run the cmdlet.

## PARAMETERS

### -Section
Specifies the sections to include in a health report.

```yaml
Type: WssReportSection
Parameter Sets: (All)
Aliases: 
Accepted values: ShowCriticalAlertsAndWarnings, ShowErrorsInEventLog, ShowServiceNotRunning, ShowSecurityAndUpdates, ShowBackups, ShowStorage, All, None

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssReportSection](./Get-WssReportSection.md)

