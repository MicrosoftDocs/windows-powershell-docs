---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/add-wssbackupvolume?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WssBackupVolume
---

# Add-WssBackupVolume

## SYNOPSIS
Adds a volume to a scheduled backup policy.

## SYNTAX

```
Add-WssBackupVolume [-BackupPolicy] <ScheduledBackupPolicy> [-BackupVolume] <BackupVolume> [<CommonParameters>]
```

## DESCRIPTION
The **Add-WssBackupVolume** cmdlet adds a volume to a scheduled backup policy.
Use the cmdlet to add volumes and the files they contain to a backup.

## EXAMPLES

### Example 1: Add a backup volume to a backup policy
```
PS C:\>$ContosoBUPolicy24 = Get-WBPolicy -Editable
PS C:\> $ContosoEmpData10 = Get-WBVolume -VolumePath F:\
PS C:\> Add-WssBackupVolume -BackupPolicy $ContosoBUPolicy24 -BackupVolume $ContosoEmpData10
```

This example adds a backup volume to scheduled backup policy.

The first command gets the current backup policy for the computer, makes it editable, and stores it in the variable named **$ContosoBUPolicy24**.

The second command creates a backup volume from drive F: and stores it in the variable named **$ContosoEmpData10**.

The third command adds the backup volume that is stored in **$ContosoEmpData10** to the scheduled backup policy that is stored in **$ContosoBUPolicy24**.

## PARAMETERS

### -BackupPolicy
Specifies the scheduled backup policy to which to add the volume.

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

### -BackupVolume
Specifies the volume to add to the scheduled backup policy.

```yaml
Type: BackupVolume
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.BackupVolume
This cmdlet returns the backup volume.

## NOTES

## RELATED LINKS

[Get-WssBackupVolume](./Get-WssBackupVolume.md)

[Remove-WssBackupVolume](./Remove-WssBackupVolume.md)

