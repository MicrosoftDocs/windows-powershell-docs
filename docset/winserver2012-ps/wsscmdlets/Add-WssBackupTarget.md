---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 5049969E-A8AE-433F-A1F0-31EDCC3B2213
manager: dansimp
---

# Add-WssBackupTarget

## SYNOPSIS
Adds a backup target to a scheduled backup.

## SYNTAX

```
Add-WssBackupTarget [-BackupPolicy] <ScheduledBackupPolicy> [-BackupTarget] <BackupTarget> [-Force]
```

## DESCRIPTION
The **Add-WssBackupTarget** cmdlet adds a backup target to a scheduled backup policy.
A scheduled backup policy is a backup file specification that has a backup schedule associated with it.
When you add a backup target to the backup policy, the backup job adds the files in the backup policy that you specify to the new target location.

## EXAMPLES

### Example 1: Add a backup target to a scheduled backup policy
```
PS C:\>$ContosoBUPolicy213 = Get-WssBackupPolicy PS C:\>$ContosoBUTarget05 = New-WBBackupTarget -VolumePath "F:\" PS C:\>Add-WssBackupTarget -BackupPolicy $ContosoBUPolicy213 -BackupTarget $ContosoBUTarget05
```

This example adds a backup target to a backup policy.

The first command gets the current backup policy for the computer and stores it in the variable named **$ContosoBUPolicy213**.

The second command creates a new backup target from the volume on drive F: and stores it in the variable named **$ContosoBUTarget05**.

The third command adds the backup target that is stored in **$ContosoBUTarget05** to the backup policy that is stored in **$ContosoBUPolicy213**.

## PARAMETERS

### -BackupPolicy
Specifies the scheduled backup policy to which to add the backup target.

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

### -BackupTarget
Specifies the backup target  to add.

```yaml
Type: BackupTarget
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssBackupTarget](./Get-WssBackupTarget.md)

[New-WssBackupTarget](./New-WssBackupTarget.md)

[Remove-WssBackupTarget](./Remove-WssBackupTarget.md)

[00000000-0000-0000-0000-000000000000](00000000-0000-0000-0000-000000000000)

