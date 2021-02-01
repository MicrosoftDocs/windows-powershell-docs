---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssBackupConfiguration
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 07332E8C-8710-4F19-B6C3-FA64EEDE0FE0
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssBackupConfiguration

## SYNOPSIS
Gets file specifications from a volume that is part of a backup.

## SYNTAX

```
Get-WssBackupConfiguration [-Volume] <BackupVolume> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssBackupConfiguration** cmdlet gets file specifications from a volume that is part of a backup.

## EXAMPLES

### Example 1: Get a backup file specification
```
PS C:\>$ContosoBUVolume13 = Get-WssBackupVolume -AllVolumes
PS C:\> $ContosoBUFSpec15 = Get-WssBackupConfiguration -Volume $ContosoBUVolume13[0]
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
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.BackupVolume

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.BackupFileSpec
This cmdlet returns the object that specifies whether files or folders are included in the server backup.

## NOTES

## RELATED LINKS

[Add-WssBackupConfiguration](./Add-WssBackupConfiguration.md)

[New-WssBackupConfiguration](./New-WssBackupConfiguration.md)

[Remove-WssBackupConfiguration](./Remove-WssBackupConfiguration.md)

