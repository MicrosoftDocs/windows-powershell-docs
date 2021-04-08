---
author: Kateyanne
external help file: WSS_Cmdlets.xml
manager: dansimp
Module Name: WssCmdlets
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/add-wssbackupsystemrecovery?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-WssBackupSystemRecovery

## SYNOPSIS
Adds a bare metal recovery option to a scheduled backup policy.

## SYNTAX

```
Add-WssBackupSystemRecovery [-BackupPolicy] <ScheduledBackupPolicy>
```

## DESCRIPTION
The **Add-WssBackupSystemRecovery** cmdlet adds a bare metal recovery option to a scheduled backup policy.
Use a backup policy with a full metal recovery option to recover the full operating system, including critical volumes, from the backup.

## EXAMPLES

### Example 1: Add a bare metal recovery option to a backup policy
```
PS C:\>$ContosoBUPolicy25 = Get-WssBackupPolicy PS C:\>Add-WssBackupSystemRecovery -BackupPolicy $ContosoBUPolicy25
```

This command adds a bare metal recovery option to a backup policy.

The first command gets the backup policy for the computer and stores it in the variable named **$ContosoBUPolicy25**.

The second command adds bare metal recovery to the backup policy that is stored in **$ContosoBUPolicy25**.

## PARAMETERS

### -BackupPolicy
Specifies the scheduled backup policy to which to add the option for bare metal recovery.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssBackupSystemRecovery](./Get-WssBackupSystemRecovery.md)

[Remove-WssBackupSystemRecovery](./Remove-WssBackupSystemRecovery.md)

