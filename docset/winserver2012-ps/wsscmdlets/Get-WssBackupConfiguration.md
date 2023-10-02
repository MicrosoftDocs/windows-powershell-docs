---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/get-wssbackupconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WssBackupConfiguration

## SYNOPSIS
Gets file specifications from a volume that is part of a backup.

## SYNTAX

```
Get-WssBackupConfiguration [-Volume] <BackupVolume>
```

## DESCRIPTION
The **Get-WssBackupConfiguration** cmdlet gets file specifications from a volume that is part of a backup.

## EXAMPLES

### Example 1: Get a backup file specification
```
PS C:\>$ContosoBUVolume13 = Get-WssBackupVolume -AllVolumes PS C:\>$ContosoBUFSpec15 = Get-WssBackupConfiguration -Volume $ContosoBUVolume13[0]
```

This example gets a backup file specification from a volume.

The first command gets the backup volumes from the server and stores them in the **$ContosoBUVolume13** variable.

The second command gets the backup file specification from the first item (located in position 0) in $ContosoBUVolume13 and stores the backup file specification in the **$ContosoBUFSpec15** variable.

## PARAMETERS

### -Volume
Specifies the volume to back up.

```yaml
Type: BackupVolume
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WssBackupConfiguration](./Add-WssBackupConfiguration.md)

[New-WssBackupConfiguration](./New-WssBackupConfiguration.md)

[Remove-WssBackupConfiguration](./Remove-WssBackupConfiguration.md)



