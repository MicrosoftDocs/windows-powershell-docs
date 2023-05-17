---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/add-wssbackupconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-WssBackupConfiguration

## SYNOPSIS
Adds a backup file specification to a volume that is part of a backup.

## SYNTAX

```
Add-WssBackupConfiguration [-Volume] <BackupVolume> [-Configuration] <BackupFileSpec>
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
Position: 2
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
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssBackupConfiguration](./Get-WssBackupConfiguration.md)

[New-WssBackupConfiguration](./New-WssBackupConfiguration.md)

[Remove-WssBackupConfiguration](./Remove-WssBackupConfiguration.md)

