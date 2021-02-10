---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Remove-WssBackupSchedule
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: E37DC420-8460-405A-8F7C-F34D49F8C3E4
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Remove-WssBackupSchedule

## SYNOPSIS
Removes a backup schedule from a scheduled backup policy.

## SYNTAX

```
Remove-WssBackupSchedule [-BackupPolicy] <ScheduledBackupPolicy> [-BackupTime] <DateTime> [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WssBackupSchedule** cmdlet removes a date and time from a scheduled backup policy.
This action removes the backup that is scheduled for that date and time from the policy.

## EXAMPLES

### Example 1: Remove a scheduled backup from a policy
```
PS C:\> Remove-WssBackupSchedule -BackupPolicy $ContosoBUPolicy25 -Schedule 5:00
```

This command removes the scheduled backup at 5:00 A.M.
daily from the policy that is stored in the variable named $ContosoBUPolicy25.

## PARAMETERS

### -BackupPolicy
Specifies the scheduled backup policy to edit.

```yaml
Type: ScheduledBackupPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -BackupTime
Specifies the date and time of the backup to remove from the schedule.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.ScheduledBackupPolicy
This cmdlet generates the **BackupPolicy** parameter value.

## NOTES

## RELATED LINKS

[Get-WssBackupSchedule](./Get-WssBackupSchedule.md)

[Add-WssBackupSchedule](./Add-WssBackupSchedule.md)

