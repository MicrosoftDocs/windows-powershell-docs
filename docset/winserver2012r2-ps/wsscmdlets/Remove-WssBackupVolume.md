---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/remove-wssbackupvolume?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WssBackupVolume
---

# Remove-WssBackupVolume

## SYNOPSIS
Removes a backup volume from a scheduled backup policy.

## SYNTAX

```
Remove-WssBackupVolume [-BackupPolicy] <ScheduledBackupPolicy> [-BackupVolume] <BackupVolume>
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WssBackupVolume** cmdlet removes a backup volume from a scheduled backup policy.
When you remove a backup volume from a scheduled backup policy, backups that use the policy no longer back up the volume.

## EXAMPLES

### Example 1: Remove a backup volume from a scheduled backup policy
```
PS C:\> Remove-WssBackupVolume -BackupPolicy $ContosoBUPolicy215 -BackupVolume $ContosoBUVol50
```

This command removes the backup volume that is stored in the variable named **$ContosoBUVol50** from the scheduled backup policy that is stored in the variable named **$ContosoBUPolicy215**.

## PARAMETERS

### -BackupPolicy
Specifies the scheduled backup policy from which to remove the backup volume.

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
Specifies the backup volume to remove from the scheduled backup policy.

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
This cmdlet generates a backup volume.

## NOTES

## RELATED LINKS

[Add-WssBackupVolume](./Add-WssBackupVolume.md)

[Get-WssBackupVolume](./Get-WssBackupVolume.md)

