---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/27/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-WBSchedule
ms.reviewer:
ms.assetid: 0C09CB71-DADA-4DF6-AF95-F7E6D5045AAA
---

# Get-WBSchedule

## SYNOPSIS
Gets the current schedule for backups.

## SYNTAX

```
Get-WBSchedule [-Policy] <WBPolicy> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WBSchedule** cmdlet gets the current schedule for backups in the **WBPolicy** object.
Backups run daily at the times specified in the schedule.
To change the schedule, use the [Set-WBSchedule](./Set-WBSchedule.md) cmdlet.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Get the scheduled backup times
```
PS C:\> $Policy = Get-WBPolicy
PS C:\> Get-WBSchedule -Policy $Policy
```

This example gets the scheduled backup times from the **WBPolicy** object.

The first command stores the result of the [Get-WBPolicy](./Get-WBPolicy.md) in the variable named $Policy.

The second command gets the backup schedule from the backup policy object.

## PARAMETERS

### -Policy
Specifies the **WBPolicy** object to display.

```yaml
Type: WBPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### WBPolicy
This cmdlet queries a specified **WBPolicy** object.

## OUTPUTS

### Datetime []
This cmdlet returns a list of **Datetime** objects in the **WBPolicy** object.

## NOTES

## RELATED LINKS

[New-WBPolicy](./New-WBPolicy.md)

[Set-WBSchedule](./Set-WBSchedule.md)

