---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/remove-wssbackuptarget?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WssBackupTarget
---

# Remove-WssBackupTarget

## SYNOPSIS
Removes a backup target from a scheduled backup policy.

## SYNTAX

```
Remove-WssBackupTarget [-BackupPolicy] <ScheduledBackupPolicy> [-BackupTarget] <BackupTarget>
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WssBackupTarget** cmdlet removes a backup target from a scheduled backup policy.
A scheduled backup policy is a backup file specification that has a backup schedule associated with it.
If you remove a backup target from a scheduled backup policy, backups that use the policy no longer back up the files and volumes that the target specifies.

## EXAMPLES

### Example 1: Remove a backup target from a policy
```
PS C:\>$ContosoBUPolicies10 = Get-WSSBackupPolicy
PS C:\> $ContosoBUTarget = Get-WssBackupTarget -BackupPolicy $ContosoBUPolicies10[9]
PS C:\> Remove-WssBackupTarget -BackupPolicy $ContosoBUPolicy10[9] -BackupTarget $ContosoBUTarget
```

This example removes a backup target from a backup policy.

The first command gets the current backup policies and stores them in the **$ContosoBUPolicies10** variable.

The second command gets the backup target for the tenth policy in the **$ContosoBUPolicies10** array, and then stores the backup target in the **$ContosoBUTarget** variable.

The third command removes the backup target that is stored in **$ContosoBUTarget** from the policy stored in **$ContosoBUPolicies10\[9\]**.

## PARAMETERS

### -BackupPolicy
Specifies the scheduled backup policy from which to remove the backup target.

```yaml
Type: ScheduledBackupPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.BackupTarget
This cmdlet generates backup targets.

## NOTES

## RELATED LINKS

[Add-WssBackupTarget](./Add-WssBackupTarget.md)

[Get-WssBackupTarget](./Get-WssBackupTarget.md)

[New-WssBackupTarget](./New-WssBackupTarget.md)

