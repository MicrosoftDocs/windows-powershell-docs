---
author: Kateyanne
external help file: WSS_Cmdlets.xml
manager: dansimp
Module Name: WssCmdlets
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/start-wssservervolumerestore?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Start-WssServerVolumeRestore

## SYNOPSIS
Starts a volume restore operation.

## SYNTAX

```
Start-WssServerVolumeRestore [-BackupSet] <BackupSet> [-VolumeToRestore] <BackupVolume>
 [-DestinationVolume] <BackupVolume> [-Confirm] [-WhatIf]
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
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DestinationVolume
Specifies a destination volume to which to restore a source volume.

```yaml
Type: BackupVolume
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
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
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS



