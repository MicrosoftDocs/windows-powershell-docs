---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 717C6443-5DD2-4126-A895-FCF31EEEA627
manager: dansimp
---

# Remove-WssBackupTarget

## SYNOPSIS
Removes a backup target from a scheduled backup policy.

## SYNTAX

```
Remove-WssBackupTarget [-BackupPolicy] <ScheduledBackupPolicy> [-BackupTarget] <BackupTarget>
```

## DESCRIPTION
The **Remove-WssBackupTarget** cmdlet removes a backup target from a scheduled backup policy.
A scheduled backup policy is a backup file specification that has a backup schedule associated with it.
If you remove a backup target from a scheduled backup policy, backups that use the policy no longer back up the files and volumes that the target specifies.

## EXAMPLES

### Example 1: Remove a backup target from a policy
```
PS C:\>$ContosoBUPolicies10 = Get-WSSBackupPolicy PS C:\>$ContosoBUTarget = Get-WssBackupTarget -BackupPolicy $ContosoBUPolicies10[9] PS C:\>Remove-WssBackupTarget -BackupPolicy $ContosoBUPolicy10[9] -BackupTarget $ContosoBUTarget
```

This example removes a backup target from a backup policy.

The first command gets the current backup policies and stores them in the variable named **$ContosoBUPolicies10**.

The second command gets the backup target for the tenth policy in the **$ContosoBUPolicies10** array, and then stores the backup target in the variable named **$ContosoBUTarget**.

The third command removes the backup target that is stored in **$ContosoBUTarget** from the policy stored in **$ContosoBUPolicies10\[9\]**.

## PARAMETERS

### -BackupPolicy
Specifies the scheduled backup policy from which to remove the backup target.

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
Specifies the name of the backup target to remove.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WssBackupTarget](./Add-WssBackupTarget.md)

[Get-WssBackupTarget](./Get-WssBackupTarget.md)

[New-WssBackupTarget](./New-WssBackupTarget.md)

