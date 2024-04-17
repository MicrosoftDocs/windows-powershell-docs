---
external help file: WSBackup_Cmdlets.xml
Module Name: WindowsServerBackup
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/get-wbdisk?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WBDisk

## SYNOPSIS
Gets a list of internal and external disks that are online for the local computer.

## SYNTAX

```
Get-WBDisk
```

## DESCRIPTION
The **Get-WBDisk** cmdlet gets a list of internal and external disks that are online for the local computer.
You can add these disks to a **WBPolicy** object that contains a backup policy by using the New-WBBackupTarget cmdlet to specify online disks as backup storage locations.

To use Windows Server® 2012 Backup cmdlets, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Get a list of disks for the local computer
```
PS C:\> $disks = Get-WBDisk

A list of WBDisk objects.
```

This command gets a list of the disks that are on the system.
You can then use the **WBDisk** object in the variable named **$disks** to specify a **WBBackupTarget** object, and use the **WBBackupTarget** object to specify where to store backups for a **WBPolicy** object that contains a backup policy.

## PARAMETERS

## INPUTS

### None
None

## OUTPUTS

### WBDisk[]
The Get-WBDisk cmdlet lists an array of **WBDisk** objects for the hard disks that the cmdlet detects on the local computer.

## NOTES

## RELATED LINKS

[Add-WBBackupTarget](./Add-WBBackupTarget.md)

[Get-WBBackupTarget](./Get-WBBackupTarget.md)

[Get-WBPolicy](./Get-WBPolicy.md)

[Get-WBVolume](./Get-WBVolume.md)

[New-WBBackupTarget](./New-WBBackupTarget.md)

[Remove-WBBackupTarget](./Remove-WBBackupTarget.md)

