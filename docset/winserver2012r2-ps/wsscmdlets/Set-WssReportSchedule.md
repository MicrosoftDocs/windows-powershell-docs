---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Set-WssReportSchedule
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: E8BFF5BE-36DF-4DDF-91A7-58EC2DB5B2FA
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Set-WssReportSchedule

## SYNOPSIS
Sets the health report schedule.

## SYNTAX

### EnableDaily (Default)
```
Set-WssReportSchedule [-Enable] [-Daily] -At <DateTimeOffset> [<CommonParameters>]
```

### Disable
```
Set-WssReportSchedule [-Disable] [<CommonParameters>]
```

### EnableHourly
```
Set-WssReportSchedule [-Enable] [-Hourly] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssReportSchedule** cmdlet sets the health report schedule.
Schedule the report to run daily, hourly, or never.

## EXAMPLES

### Example 1: Set the report schedule
```
PS C:\> $Time = [System.DateTimeOffset]::Now
PS C:\> Set-WssReportSchedule -Enable -Daily -At $Time
```

The first command gets the current time and stores the result in the $Time variable.

The second command sets the report schedule to run daily at the time specified by the $Time variable.

## PARAMETERS

### -At
Specifies the time of day to run the daily health report.

```yaml
Type: DateTimeOffset
Parameter Sets: EnableDaily
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Daily
Indicates that the schedule runs the health report daily.

```yaml
Type: SwitchParameter
Parameter Sets: EnableDaily
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Disable
Indicates that the automated health report generation is disabled.

```yaml
Type: SwitchParameter
Parameter Sets: Disable
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Enable
Indicates that the automated health report generation is enabled.

```yaml
Type: SwitchParameter
Parameter Sets: EnableDaily, EnableHourly
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Hourly
Indicates that the schedule runs the health report hourly.

```yaml
Type: SwitchParameter
Parameter Sets: EnableHourly
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssReportSchedule](./Get-WssReportSchedule.md)

