---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/remove-wbcatalog?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WBCatalog
---

# Remove-WBCatalog

## SYNOPSIS
Removes the backup catalog from the local computer.

## SYNTAX

```
Remove-WBCatalog [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WBCatalog** cmdlet removes the backup catalog from the local computer.
Use this cmdlet when the backup catalog is corrupted and you cannot restore it by using the [Restore-WBCatalog](./Restore-WBCatalog.md) cmdlet.

If you remove the backup catalog for a computer, you cannot access the backups of that computer by using Windows Server Backup.
In this case, if you can access another backup location, use **Restore-WBCatalog** to restore the backup catalog from that location, and then create a new backup from that backup catalog.

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
Because the command does not include the *Force* parameter, the command asks for confirmation before it removes the catalog.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Restore-WBCatalog](./Restore-WBCatalog.md)

