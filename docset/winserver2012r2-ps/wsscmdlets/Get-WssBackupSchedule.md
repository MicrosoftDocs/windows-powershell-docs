---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssBackupSchedule
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-12-05
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 72B9E0E4-F92B-419F-93C3-1B1FBD595E4D
ms.author: kenwith
ms.reviewer: brianlic
---

# Get-WssBackupSchedule

## SYNOPSIS
Gets the backup schedule from a scheduled backup policy.

## SYNTAX

```
Get-WssBackupSchedule [-BackupPolicy] <ScheduledBackupPolicy> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssBackupSchedule** cmdlet gets the backup schedule from a scheduled backup policy.

## EXAMPLES

### Example 1: Get a backup schedule from a scheduled backup policy
```
PS C:\>$ContosoBUPolicy25 = Get-WssBackupPolicy
PS C:\> Get-WssBackupSchedule -BackupPolicy $ContosoBUPolicy25
```

This example gets the backup schedule from a scheduled backup policy.

The first command gets the backup policy for the computer and stores the result in the **$ContosoBUPolicy25** variable

The second command gets the backup schedule from the scheduled backup policy stored in $ContosoBUPolicy25$ContosoBUSched25.

## PARAMETERS

### -BackupPolicy
Specifies the scheduled backup policy from which  to get the schedule.

```yaml
Type: ScheduledBackupPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.DateTime
This cmdlet returns a list of backup schedule times.

## NOTES

## RELATED LINKS

[Add-WssBackupSchedule](./Add-WssBackupSchedule.md)

[Remove-WssBackupSchedule](./Remove-WssBackupSchedule.md)

