---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: E37DC420-8460-405A-8F7C-F34D49F8C3E4
manager: dansimp
---

# Remove-WssBackupSchedule

## SYNOPSIS
Removes a backup schedule from a scheduled backup policy.

## SYNTAX

```
Remove-WssBackupSchedule [-BackupPolicy] <ScheduledBackupPolicy> [-BackupTime] <DateTime>
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
Position: 1
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
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WssBackupSchedule](./Add-WssBackupSchedule.md)

[Remove-WssBackupSchedule](./Remove-WssBackupSchedule.md)

