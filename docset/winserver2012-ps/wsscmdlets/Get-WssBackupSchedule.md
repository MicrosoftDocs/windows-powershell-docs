---
author: Kateyanne
external help file: WSS_Cmdlets.xml
manager: dansimp
Module Name: WssCmdlets
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssbackupschedule?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WssBackupSchedule

## SYNOPSIS
Gets the backup schedule from a scheduled backup policy.

## SYNTAX

```
Get-WssBackupSchedule [-BackupPolicy] <ScheduledBackupPolicy>
```

## DESCRIPTION
The **Get-WssBackupSchedule** cmdlet gets the backup schedule from a scheduled backup policy.

## EXAMPLES

### Example 1: Get a backup schedule from a scheduled backup policy
```
PS C:\>$ContosoBUPolicy25 = Get-WssBackupPolicy PS C:\> Get-WssBackupSchedule -BackupPolicy $ContosoBUPolicy25
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
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssBackupSchedule](./Get-WssBackupSchedule.md)

[Remove-WssBackupSchedule](./Remove-WssBackupSchedule.md)

