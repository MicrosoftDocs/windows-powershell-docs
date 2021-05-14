---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/add-wssbackupschedule?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-WssBackupSchedule

## SYNOPSIS
Adds a date and time to a backup policy for use as a backup schedule.

## SYNTAX

```
Add-WssBackupSchedule [-BackupPolicy] <ScheduledBackupPolicy> [-BackupTime] <DateTime>
```

## DESCRIPTION
The **Add-WssBackupSchedule** cmdlet adds a date and time to a backup policy.
The backup process uses this date and time as a backup schedule.

## EXAMPLES

### Example 1: Add a backup schedule to a backup policy
```
PS C:\>$ContosoBUPolicy25 = Get-WssBackupPolicy PS C:\>Add-WssBackupSchedule -BackupPolicy $ContosoBUPolicy25 -BackupTime 5:00
```

This example adds a backup schedule to a backup policy.

The first command gets the backup policy for the computer and stores it in the **$ContosoBUPolicy25** variable.

The second command adds 5:00 A.M.
daily as a backup schedule for the backup policy stored in **$ContosoBUPolicy25**.

## PARAMETERS

### -BackupPolicy
Specifies the backup policy to which to add the backup schedule.

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
Specifies the backup date and time to add to the scheduled backup policy.

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

[Get-WssBackupSchedule](./Get-WssBackupSchedule.md)

[Remove-WssBackupSchedule](./Remove-WssBackupSchedule.md)

