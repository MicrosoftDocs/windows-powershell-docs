---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/remove-wssbackupconfiguration?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WssBackupConfiguration
---

# Remove-WssBackupConfiguration

## SYNOPSIS
Removes a file specification from a backup volume.

## SYNTAX

```
Remove-WssBackupConfiguration [-Volume] <BackupVolume> [-Configuration] <BackupFileSpec> [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WssBackupConfiguration** cmdlet removes a file specification from a backup volume.
When you remove a file specification from a backup volume, the files and folders in the file specification are no longer backed up with the backup volume.

## EXAMPLES

### Example 1: Remove a file specification from a backup volume
```
PS C:\>$ContosoBUVolume110 = Get-WssBackupVolume -AllVolumes
PS C:\> $ContosoBUFilespec05 = Get-WssBackupConfiguration -Volume $ContosoBUVolume110[0]
PS C:\> Remove-WssBackupConfiguration -Configuration $ContosoBUFilespec05[1]
```

This command removes the backup file specification from a backup volume.

The first command gets the backup volumes from the server and stores them in the **$ContosoBUVolume110** variable.

The second command gets the backup file specification from the first item (located in position 0) in **$ContosoBUVolume110** and stores the backup file specification in the **$ContosoBUFilespec05** variable.

The third command removes the backup file specification from the second item (located in position 1) in **$ContosoBUFilespec05**.

## PARAMETERS

### -Configuration
Specifies the backup file specification to remove from the volume.

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
Specifies the volume from which to remove the file specification.

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

### Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.BackupVolume

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.BackupFileSpec
This cmdlet generates an object that indicates whether to include or exclude files or folders in the server backup.

## NOTES

## RELATED LINKS

[Add-WssBackupConfiguration](./Add-WssBackupConfiguration.md)

[Get-WssBackupConfiguration](./Get-WssBackupConfiguration.md)

[New-WssBackupConfiguration](./New-WssBackupConfiguration.md)

