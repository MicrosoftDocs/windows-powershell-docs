---
external help file: WSBackup_Cmdlets.xml
Module Name: WindowsServerBackup
online version: https://docs.microsoft.com/powershell/module/windowsserverbackup/restore-wbcatalog?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Restore-WBCatalog

## SYNOPSIS
Recovers a backup catalog for the local computer from a storage location.

## SYNTAX

```
Restore-WBCatalog [-Force] [-BackupTarget] <WBBackupTarget>
```

## DESCRIPTION
The **Restore-WBCatalog** cmdlet recovers a backup catalog for the local computer from a storage location that you specify.

If the location (disk, DVD, or remote shared folder) where you store your backups is damaged or lost and you cannot use it to restore the backup catalog, use the Remove-WBCatalog cmdlet to delete the corrupted catalog.
Then, create a new backup after the cmdlet finishes deleting your backup catalog.

## EXAMPLES

### Example 1: Restore a backup catalog
```
PS C:\> Restore-WBCatalog -BackupTarget $Bt -Force

3 backups found in the specified target.
WARNING: The backup information on this location has details of backups created
up to 12/8/2011 11:41:38 AM. You may not be able to access backups created
after this date when the catalog recovery operation completes.
The catalog has been successfully recovered.
```

This command recovers the backup catalog from the backup target in the variable named **$Bt**.
The cmdlet displays a warning that gives details about the backups present in the backup target.
The cmdlet also displays a message that confirms that it has successfully recovered the catalog.

## PARAMETERS

### -BackupTarget
Specifies a backup target object that contains the storage location where backups from which the cmdlet restores the catalog reside.

```yaml
Type: WBBackupTarget
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Force
Indicates that the cmdlet recovers the catalog without prompting you for confirmation.
By default, the cmdlet prompts you for confirmation before it proceeds.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### WBBackupTarget, SwitchParameter
Specifies a backup target object from which to restore the catalog.
Use the **Force** parameter to suppress the confirmation message.

## OUTPUTS

### System.String
Specifies a warning that gives details about the backups present in the backup target and a message that confirms that the cmdlet successfully recovered the catalog.

## NOTES

## RELATED LINKS



[Remove-WBCatalog](./Remove-WBCatalog.md)

