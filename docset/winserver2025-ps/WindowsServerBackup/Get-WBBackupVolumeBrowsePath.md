---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/get-wbbackupvolumebrowsepath?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WBBackupVolumeBrowsePath
---

# Get-WBBackupVolumeBrowsePath

## SYNOPSIS
Mounts a volume inside a backup so that you can browse the files on the volume.

## SYNTAX

```
Get-WBBackupVolumeBrowsePath [-BackupSet] <WBBackupSet> [-VolumeInBackup] <WBVolume> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WBBackupVolumeBrowsePath** cmdlet mounts a volume in a **WBBackup** object that contains a backup so that you can browse the files on the volume.
You can use the path that this cmdlet returns as a parameter to a [Start-WBFileRecovery](./Start-WBFileRecovery.md) cmdlet to specify a file recovery path.

## EXAMPLES

### Example 1: Get a mount path for a backup volume
```
PS C:\> $Backups = Get-WBBackupSet
PS C:\> Get-WBBackupVolumeBrowsePath -BackupSet $Backup -VolumeInBackup $Backup.Volume[1]

\\Server01\WsbMountedVolumes\WsbMountedVolumeFile13_6fc68703-1c22-11e1-89cd-806e6f6e6963\
```

This example gets the mount path for a backup volume.

The first command gets server backups from the system catalog and store them in the variable named $Backups.

The second command mounts the volume in element 1 of the Volume array within the backup object in the variable named $Backup.

## PARAMETERS

### -BackupSet
Specifies a **WBBackupSet** object that contains the backup set from which to mount the volume.

```yaml
Type: WBBackupSet
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VolumeInBackup
Specifies a **WBVolume** object that contains the volume in the backup set object to mount for browsing.
This parameter must be an object from the **WBBackupSet.Volume** array.

```yaml
Type: WBVolume
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Windows.ServerBackup.Commands.WBBackupSet

### Microsoft.Windows.ServerBackup.Commands.WBVolume

You must specify the **WBBackupSet** object that contains the backup set along with the **WBVolume** object that contains the volume inside the backup set.

## OUTPUTS

### System.Object

This cmdlet returns the mount path for the volume that you back up if the mount is successful.
You can use the mount path with a dir command to browse the volume or specify the file recovery path as a parameter to the **Start-WBFileRecovery** cmdlet.
This path is valid for only 10 minutes, and Windows Server® 2012 Backup deletes the mount path after that.
To continue browsing this path, call the **Get-WBBackupVolumeBrowsePath** cmdlet again with the same parameters within the 10-minute interval to make the path valid again for 10 more minutes, and repeat the process as needed.

## NOTES

## RELATED LINKS

[Start-WBFileRecovery](./Start-WBFileRecovery.md)

