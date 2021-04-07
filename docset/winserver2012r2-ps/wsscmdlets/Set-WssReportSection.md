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
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/set-wssreportsection?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WssReportSection
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

