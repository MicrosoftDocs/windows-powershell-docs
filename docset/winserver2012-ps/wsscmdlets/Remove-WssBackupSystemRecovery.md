---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/remove-wssbackupsystemrecovery?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-WssBackupSystemRecovery

## SYNOPSIS
Removes a bare metal recovery option from a scheduled backup policy.

## SYNTAX

```
Remove-WssBackupSystemRecovery [-BackupPolicy] <ScheduledBackupPolicy>
```

## DESCRIPTION
The **Remove-WssBackupSystemRecovery** cmdlet removes a bare metal recovery option from a scheduled backup policy.
If you remove bare metal recovery from a scheduled backup policy, disaster recovery may not be possible.

## EXAMPLES

### Example 1: Remove a bare metal recovery option from a backup policy
```
PS C:\> Remove-WssBackupSystemRecovery -BackupPolicy $ContosoBUPolicy25
```

This command removes a bare metal recovery option from the backup policy that is stored in the variable named **$ContosoBUPolicy25**.

## PARAMETERS

### -BackupPolicy
Specifies the scheduled backup policy from which to remove the system recovery option.

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

[Add-WssBackupSystemRecovery](./Add-WssBackupSystemRecovery.md)

[Get-WssBackupSystemRecovery](./Get-WssBackupSystemRecovery.md)

