---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Start-WssServerVolumeRestore
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: C87E8B65-3310-41FF-898C-7B678AB9B611
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Start-WssServerVolumeRestore

## SYNOPSIS
Starts a volume restore operation.

## SYNTAX

```
Start-WssServerVolumeRestore [-BackupSet] <BackupSet> [-VolumeToRestore] <BackupVolume>
 [-DestinationVolume] <BackupVolume> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-WssServerVolumeRestore** cmdlet starts a volume restore operation on a sbs_sbs8_2 server.

## EXAMPLES

### Example 1: Restore a volume
```
PS C:\> $Policy = Get-WssBackupPolicy
PS C:\> $Source = Get-WssBackupVolume -BackupPolicy $Policy
PS C:\> $Destination = Get-WssBackupVolume -AllVolumes
PS C:\> $Backupset = Get-WssBackupSet
PS C:\> Start-WssServerVolumeRestore -BackupSet $Backupset[0] -VolumeToRestore $Source[2] -DestinationVolume $Destination[2]
```

This example restores a volume from a backup set.

The first command uses the **Get-WssBackupPolicy** cmdlet to get the current backup policy, and stores the results in the variable $Policy.

The second command uses the **Get-WssBackupVolume** cmdlet to get the backup volumes that are backed up with this policy, and stores the result in the variable named **$Source**.

The third command uses the **Get-WssBackupVolume** cmdlet to get the volumes on the system, and stores the result in the variable named **$Destination**.

The fourth command uses the **Get-WssBackupSet** cmdlet to retrieve the backup sets, and stores the result in the variable named **$Backupset**.

The fifth command uses the **Get-WssServerVolumeRestore** cmdlet to restore the volume.

## PARAMETERS

### -BackupSet
Specifies a backup set from which to restore a volume.

```yaml
Type: BackupSet
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationVolume
Specifies a destination volume to which to restore a source volume.

```yaml
Type: BackupVolume
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeToRestore
Specifies a source volume to restore.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

