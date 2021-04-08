---
author: Kateyanne
external help file: WSS_Cmdlets.xml
manager: dansimp
Module Name: WssCmdlets
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/new-wssbackuptarget?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-WssBackupTarget

## SYNOPSIS
Creates a backup target from a backup disk.

## SYNTAX

```
New-WssBackupTarget [-Disk] <BackupDisk> [[-Label] <String>] [-PreserveExistingBackups]
```

## DESCRIPTION
The **New-WssBackupTarget** cmdlet creates a backup target from a backup disk.
A backup target defines storage locations for backups.

## EXAMPLES

### Example 1: Create a backup target from a backup disk
```
PS C:\> New-WssBackupTarget -Disk $disks[1] -Label "Backup Disk 1" -PreserveExistingBackups
```

This command creates a backup target labeled Backup Disk 1 from the second item, located in position 1, of the array that is stored in the **$disks** variable.

## PARAMETERS

### -Disk
Specifies the backup disk that stores backups.

```yaml
Type: BackupDisk
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Label
Specifies the label for the backup storage location.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreserveExistingBackups
Indicates that the cmdlet keeps existing backups on the disk in the **BackupDisk** parameter when the cmdlet adds a new backup to the disk.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WssBackupTarget](./Add-WssBackupTarget.md)

[Get-WssBackupTarget](./Get-WssBackupTarget.md)

[Remove-WssBackupTarget](./Remove-WssBackupTarget.md)

