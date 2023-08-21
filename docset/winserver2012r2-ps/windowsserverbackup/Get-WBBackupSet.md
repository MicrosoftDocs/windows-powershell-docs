---
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/get-wbbackupset?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WBBackupSet
---

# Get-WBBackupSet

## SYNOPSIS
Gets backups for a server from a location that you specify.

## SYNTAX

```
Get-WBBackupSet [[-BackupTarget] <WBBackupTarget>] [[-MachineName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WBBackupSet** cmdlet gets a list of **WBBackupSet** objects that contain backups for a server from a location that you specify.
A **WBBackupSet** object contains information about the backup time and date, the backed-up computer, the backup type, and the items that were part of the backup.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Get server backups from the system catalog
```
PS C:\> $Backups = Get-WBBackupSet
```

This command gets server backups from the system catalog and stores them in the **$Backups** variable.

### Example 2: Get server backups from a specific location
```
PS C:\> $BackupLocation = New-WBBackupTarget -VolumePath D:
PS C:\> $Backups = Get-WBBackupSet -BackupTarget $BackupLocation
```

This example queries the catalog at a specific storage location for backups.

The first command creates a backup target on the volume that has the drive letter D: and stores this location in the variable named **$BackupLocation**.

The second command gets backup data from the backup target in **$BackupLocation** and then stores this data in the variable named **$Backups**.

## PARAMETERS

### -BackupTarget
Specifies a **WBBackupTarget** object.
This object includes the storage location that contains the backups for which you want details.

Use this parameter to get information about backups of computers other than the local computer.
The cmdlet lists the backup sets from the catalog on the computer that you specify, not from the system catalog of the local computer.
Alternate locations can be locally attached disk drives or remote shared folders.

When you specify this parameter along with the **MachineName** parameter, the cmdlet returns backup information from the storage location that you specify in this parameter.
This storage location is on the server that you specify in the **MachineName** parameter.

```yaml
Type: WBBackupTarget
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MachineName
Specifies the computer for which you want backup details.

Use this parameter when backups of different computers appear in the same location or when you use the **BackupTarget** parameter to specify a storage location that contains the backup details.

When you specify this parameter along with the **BackupTarget** parameter, the cmdlet returns backup information from the storage location that you specify in the **BackupTarget** parameter.
The storage location is on the server that you specify in this parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### WBBackupTarget
The Get-WBBackupSet cmdlet uses a **WBBackupTarget** object to determine the computer from which to load the catalog and get backup information.

## OUTPUTS

### WBBackupSet[]
The Get-WBBackupSet cmdlet displays the list of **WBBackupSet** objects from the local system catalog or from the catalog on the computer that stores the backup sets.
The **WBBackupTarget** parameter specifies the location of this computer.

## NOTES

## RELATED LINKS

[Get-WBBackupTarget](./Get-WBBackupTarget.md)

[New-WBBackupTarget](./New-WBBackupTarget.md)

[Remove-WBBackupSet](./Remove-WBBackupSet.md)

