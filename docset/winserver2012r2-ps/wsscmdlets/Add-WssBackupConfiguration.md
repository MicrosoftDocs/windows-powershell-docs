---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/add-wssbackupconfiguration?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WssBackupConfiguration
---

# Add-WssBackupConfiguration

## SYNOPSIS
Adds a backup file specification to a volume that is part of a backup.

## SYNTAX

```
Add-WssBackupConfiguration [-Volume] <BackupVolume> [-Configuration] <BackupFileSpec> [<CommonParameters>]
```

## DESCRIPTION
The **Add-WssBackupConfiguration** cmdlet adds a backup file specification to a volume that is part of a backup.

## EXAMPLES

### Example : 1: Add a backup file specification to a volume
```
PS C:\>$ContosoBUVolume10 = Get-WssBackupVolume -AllVolumes PS C:\>$ContosoBUConfig10 = Get-WssBackupConfiguration -Volume $ContosoBUVolume10[3] PS C:\>Add-WssBackupConfiguration -FileSpec $ContosoBUConfig10 -Volume $ContosoBUVolume10[5]
```

This example adds a backup configuration to a backup volume.

The first command gets a list of backup volumes from the server and stores them in the variable named $ContosoBUVolume10.

The second command gets the backup file specification from the fourth item (located in position 3) in the $ContosoBUVolume10 array.

The third command adds the backup file specification in $ContosoBUConfig10 to the sixth item (located in position 5) in the $ContosoBUVolume10 array.

## PARAMETERS

### -Configuration
Specifies the backup file specification to add.

```yaml
Type: BackupFileSpec
Parameter Sets: (All)
Aliases: Config

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Volume
Specifies the volume on which to create the backup file specification.

```yaml
Type: BackupVolume
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.BackupVolume
This cmdlet generates the backup source volume with the added file specification.

## NOTES

## RELATED LINKS

[Get-WssBackupConfiguration](./Get-WssBackupConfiguration.md)

[New-WssBackupConfiguration](./New-WssBackupConfiguration.md)

[Remove-WssBackupConfiguration](./Remove-WssBackupConfiguration.md)

