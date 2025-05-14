---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/new-wbbackuptarget?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-WBBackupTarget
---

# New-WBBackupTarget

## SYNOPSIS
Creates a backup target object.

## SYNTAX

### Disk
```
New-WBBackupTarget [-Disk] <WBDisk> [[-Label] <String>] [[-PreserveExistingBackups] <Boolean>]
 [<CommonParameters>]
```

### Volume
```
New-WBBackupTarget [-Volume] <WBVolume> [<CommonParameters>]
```

### VolumePath
```
New-WBBackupTarget [-VolumePath] <String> [<CommonParameters>]
```

### NetworkWithPSCred
```
New-WBBackupTarget [-NetworkPath] <String> [[-Credential] <PSCredential>] [-NonInheritAcl] [<CommonParameters>]
```

### RemovableDrive
```
New-WBBackupTarget [-RemovableDrive] <String> [<CommonParameters>]
```

## DESCRIPTION
The **New-WBBackupTarget** cmdlet creates a backup target object for Windows Server Backup.
The backup target object defines the locations where the server stores backups.

To use this cmdlet, you must be a member of the Administrators or Backup Operators group.

## EXAMPLES

### Example 1: Use a disk as a backup target
```
PS C:\> $Disks = Get-WBDisk
PS C:\> $DiskBackupLocation = New-WBBackupTarget -Disk $Disks[1] -Label "Backup Disk 1"
```

This example creates a **WBBackupTarget** object that uses the disk labeled Backup Disk 1 as the backup target.

The first command gets the disks that are available for backup storage and stores them in a variable named $Disks.

The second command sets the first disk stored in the $Disks array as the backup target and assigns the label Backup Disk 1 to that disk.
The disk is available to store backups only after the server calls the [Set-WBPolicy](./Set-WBPolicy.md) cmdlet and specifies the **WBPolicy** object to which it added the backup target.
You can add multiple storage disks to this backup policy.

### Example 2: Use a remote shared folder as a backup target
```
PS C:\> $Cred = Get-Credential
PS C:\> $NetworkBackupLocation = New-WBBackupTarget -NetworkPath "\\Server01\BackupStorageLocation" -Credential $Cred
```

This example creates a **WBBackupTarget** object that uses a remote shared folder named \\\\Server01\BackupStorageLocation as the backup storage location and stores permissions to the credentials in a variable named $Cred.
The server needs these credentials to access the shared folder.
If you use a remote shared folder, you can add only one backup location to the **WBPolicy** object that contains the backup policy.

The first command gets credentials and stores them in a variable named $Cred.

The second command specifies the remote shared folder named \\\\Server01\BackupStorageLocation as the backup target and the credentials in $Cred as the credentials for the operation.

### Example 3: Specify a volume as a backup target by using a drive letter
```
PS C:\> $volumeBackupLocation = New-WBBackupTarget -VolumePath "D:"
```

This command creates a **WBBackupTarget** object that uses a volume with drive letter D: as the backup storage location.
You can add multiple volumes for storage to the **WBPolicy** object that contains the backup policy.

### Example 4: Specify a volume as a backup target by using an array element
```
PS C:\> $VolumeList = Get-WBVolume -AllVolumes
PS C:\> $VolumeBackupLocation = New-WBBackupTarget -Volume $VolumeList[3]
```

This example creates a **WBBackupTarget** object that uses a volume whose name appears in an array element as the backup storage location.
You can add multiple volumes for storage to the **WBPolicy** object that contains the backup policy.

The first command stores the names of all volumes in an array variable named $VolumeList.

The second command creates the backup target by using the volume name stored in the third element of the $VolumeList array and stores the **WBBackupTarget** object in the variable named $VolumeBackupLocation.

### Example 5: Specify a volume as a backup target by using the letter of a removable drive
```
PS C:\> $DvdBackupTarget = New-WBBackupTarget -RemovableDrive "G:"
```

This command creates a **WBBackupTarget** object that uses a DVD drive, G:, as the backup storage location and stores the **WBBackupTarget** object in a variable named $DvdBackupTarget.

You can add only one DVD target as a backup policy to a **WBPolicy** object that contains a backup policy, and you can specify only volume backup and recovery when you use a DVD as a target type.

## PARAMETERS

### -Credential
Specifies a **PSCredential** object that contains the user name and password for a user account that has access permissions for a location where the server stores backups.

To obtain a credential object, use the **Get-Credential** cmdlet.
For more information, type `Get-Help Get-Credential`.

```yaml
Type: PSCredential
Parameter Sets: NetworkWithPSCred
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Disk
Specifies a **WBDisk** object that contains the disk where the server stores backups.

Use this parameter if the storage location for the backup is a disk.
Use the Get-WBDisk cmdlet to see which disks are available, and then use this parameter to specify the disk that you want to use.

```yaml
Type: WBDisk
Parameter Sets: Disk
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Label
Specifies a label for the backup storage.

```yaml
Type: String
Parameter Sets: Disk
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkPath
Specifies the path to the remote shared folder in which the server stores backups.

Use this parameter if the storage location is a remote shared folder (on a network).
You can specify the *NonInheritAcl* parameter for this type of storage location, but only for one-time backups.
You can also use the *Credential* parameter to specify who can access the backups.

```yaml
Type: String
Parameter Sets: NetworkWithPSCred
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NonInheritAcl
Indicates that the server applies access control list (ACL) permissions for the credentials that the parameter *Credential* specifies to \\\\ServerName\ShareName\WindowsImageBackup\ComputerBackedUp\BackupFolder.
To access the backup later, you must use these credentials or be a member of the Administrators group or the Backup Operators group on the computer that has the shared folder.

This parameter applies only to one-time backups and not to scheduled backups.

We recommend that you use this parameter to manage permissions for backups.
If you do not use this parameter, Windows Server Backup applies the ACL permissions from the remote shared folder to the ComputerBackedUp folder so that anyone who can access the remote shared folder can also access the backup.

```yaml
Type: SwitchParameter
Parameter Sets: NetworkWithPSCred
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreserveExistingBackups
Indicates whether the server saves copies of previous backups each time it performs a new backup.

If you save a backup to a remote shared folder, the server overwrites that backup if you use the same folder to back up the same computer again.
In addition, if the backup operation fails and the server overwrites the older backup, the newer backup will not be usable.
To avoid this situation, specify this parameter, and create subfolders in the remote shared folder to organize your backups.
If you do this, the subfolders need twice the space of the parent folder.

```yaml
Type: Boolean
Parameter Sets: Disk
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemovableDrive
Specifies the drive letter of the DVD or removable drive that you use as a backup target.
You can back up only whole volumes to this media type, and volume recovery is the only available recovery type.
You cannot use this backup location to back up or recover system states, files, Hyper-V virtual servers, or applications.

The server detects a DVD drive as a valid target only if the drive contains a disc.

```yaml
Type: String
Parameter Sets: RemovableDrive
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Volume
Specifies a **WBVolume** object that contains the volume that stores the backups.
To get a **WBVolume** object, use the Get-WBVolume cmdlet.

Use this parameter if the storage location is a volume.
You can get a list of all volumes available by using the `Get-WBVolume -AllVolumes` cmdlet.
Then, choose the **WBVolume** object for the storage location that you want to use.

This parameter provides the only way that you can specify Universal Naming Convention (UNC) path volumes, which are not mounted, as backup storage locations.

```yaml
Type: WBVolume
Parameter Sets: Volume
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VolumePath
Specifies the drive letter of the volume that stores backups.

```yaml
Type: String
Parameter Sets: VolumePath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Windows.ServerBackup.Commands.WBDisk

### Microsoft.Windows.ServerBackup.Commands.WBVolume

### System.Management.Automation.PSCredential

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Add-WBBackupTarget](./Add-WBBackupTarget.md)

[Get-WBDisk](./Get-WBDisk.md)

[Get-WBVolume](./Get-WBVolume.md)

[Get-Credential](https://go.microsoft.com/fwlink/?LinkID=293936)

