---
external help file: WSBackup_Cmdlets.xml
Module Name: WindowsServerBackup
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/remove-wbcatalog?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-WBCatalog

## SYNOPSIS
Removes the backup catalog from the local computer.

## SYNTAX

```
Remove-WBCatalog [-Force]
```

## DESCRIPTION
The **Remove-WBCatalog** cmdlet removes the backup catalog from the local computer.
Use this cmdlet when the backup catalog is corrupted and you cannot restore it by using the Restore-WBCatalog cmdlet.

If you remove the backup catalog for a computer, you cannot access the backups of that computer by using Windows Server® 2012 Backup.
In this case, if you can access another backup location, use Restore-WBCatalog to restore the backup catalog from that location, and then create a new backup from that backup catalog.

## EXAMPLES

### Example 1: Remove a backup catalog
```
PS C:\> Remove-WBCatalog

Warning
Are you sure that you want to delete the backup catalog? If you delete the
catalog, you will need to create a new set of backups.
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
The backup catalog has been successfully deleted.
```

This command removes the backup catalog.
Because the command does not include the **Force** parameter, the command asks for confirmation before it removes the catalog.

## PARAMETERS

### -Force
Indicates that the cmdlet removes the catalog without prompting you for confirmation.
By default, the cmdlet prompts you for confirmation before it proceeds.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### SwitchParameter
You can specify the **Force** parameter to suppress the confirmation message for the cmdlet.

## OUTPUTS

### System.String
String that indicates that the cmdlet has deleted the catalog.

## NOTES

## RELATED LINKS



[Restore-WBCatalog](./Restore-WBCatalog.md)

