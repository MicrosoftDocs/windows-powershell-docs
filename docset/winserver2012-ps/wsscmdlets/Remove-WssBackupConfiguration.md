---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/remove-wssbackupconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-WssBackupConfiguration

## SYNOPSIS
Removes a file specification from a backup volume.

## SYNTAX

```
Remove-WssBackupConfiguration [-Volume] <BackupVolume> [-Configuration] <BackupFileSpec>
```

## DESCRIPTION
The **Remove-WssBackupConfiguration** cmdlet removes a file specification from a backup volume.
When you remove a file specification from a backup volume, the files and folders in the file specification are no longer backed up with the backup volume.

## EXAMPLES

### Example 1: Remove a file specification from a backup volume
```
PS C:\>$ContosoBUVolume110 = Get-WssBackupVolume -AllVolumes PS C:\>$ContosoBUFilespec05 = Get-WssBackupConfiguration -Volume $ContosoBUVolume110[0] PS C:\>Remove-WssBackupConfiguration -Configuration $ContosoBUFilespec05[1]
```

This command removes the backup file specification from a backup volume.

The first command gets the backup volumes from the server and stores them in the variable named $ContosoBUVolume110.

The second command gets the backup file specification from the first item (located in position 0) in $ContosoBUVolume110 and stores the backup file specification in the variable named $ContosoBUFilespec05.

The third command removes the backup file specification from the second item (located in position 1) in $ContosoBUFilespec05.

## PARAMETERS

### -Configuration
Specifies the backup file specification to remove from the volume.

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
Specifies the volume from which to remove the file specification.

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

[Add-WssBackupConfiguration](./Add-WssBackupConfiguration.md)

[Get-WssBackupConfiguration](./Get-WssBackupConfiguration.md)

[New-WssBackupConfiguration](./New-WssBackupConfiguration.md)

