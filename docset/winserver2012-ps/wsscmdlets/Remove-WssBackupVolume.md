---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: A6E70E57-DDC7-4954-9E68-0F089A4FB093
manager: dansimp
---

# Remove-WssBackupVolume

## SYNOPSIS
Removes a backup volume from a scheduled backup policy.

## SYNTAX

```
Remove-WssBackupVolume [-BackupPolicy] <ScheduledBackupPolicy> [-BackupVolume] <BackupVolume>
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
Position: 1
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
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WssBackupVolume](./Add-WssBackupVolume.md)

[Get-WssBackupVolume](./Get-WssBackupVolume.md)

