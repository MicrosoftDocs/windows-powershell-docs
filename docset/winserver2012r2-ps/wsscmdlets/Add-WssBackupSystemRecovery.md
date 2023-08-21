---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/add-wssbackupsystemrecovery?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WssBackupSystemRecovery
---

# Add-WssBackupSystemRecovery

## SYNOPSIS
Adds a bare metal recovery option to a scheduled backup policy.

## SYNTAX

```
Add-WssBackupSystemRecovery [-BackupPolicy] <ScheduledBackupPolicy> [<CommonParameters>]
```

## DESCRIPTION
The **Add-WssBackupSystemRecovery** cmdlet adds a bare metal recovery option to a scheduled backup policy.
Use a backup policy with a full metal recovery option to recover the full operating system, including critical volumes, from the backup.

## EXAMPLES

### Example 1: Add a bare metal recovery option to a backup policy
```
PS C:\>$ContosoBUPolicy25 = Get-WssBackupPolicy
PS C:\> Add-WssBackupSystemRecovery -BackupPolicy $ContosoBUPolicy25
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
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.ScheduledBackupPolicy
This cmdlet returns the BackupPolicy parameter.

## NOTES

## RELATED LINKS

[Get-WssBackupSystemRecovery](./Get-WssBackupSystemRecovery.md)

[Remove-WssBackupSystemRecovery](./Remove-WssBackupSystemRecovery.md)

