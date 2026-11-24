---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/remove-wbbackuptarget?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WBBackupTarget
---

# Remove-WBBackupTarget

## SYNOPSIS
Removes backup storage locations from a backup policy.

## SYNTAX

```
Remove-WBBackupTarget [-Policy] <WBPolicy> [-Target] <WBBackupTarget> [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WBBackupTarget** cmdlet removes backup storage locations from a backup policy.
**WBBackupTarget** objects define backup storage locations.
A **WBPolicy** object defines the backup policy.

Before you can remove a backup target from a **WBPolicy** object, you must put the **WBPolicy** object in edit mode.
To put the **WBPolicy** object in edit mode for a policy that you have set as the scheduled backup policy, use the [Get-WBPolicy](./Get-WBPolicy.md) cmdlet with the *Editable* parameter.
The [New-WBPolicy](./New-WBPolicy.md) cmdlet creates a new **WBPolicy** object that is already in edit mode.

If you specify a disk as a storage location for backups, the server formats the disk before use and permanently deletes any existing data on the disk.

You can add only one storage type at a time to a policy.
If you specify a shared folder as the storage location, you cannot add more locations because you can specify only one shared folder as a storage location at any time.
However, you can specify multiple disks or volumes at one time by calling the [Add-WBBackupTarget](./Add-WBBackupTarget.md) cmdlet for each location.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Remove a backup target from a backup policy
```
PS C:\> $Policy = Get-WBPolicy
PS C:\> $BackupLocations = Get-WBBackupTarget -Policy $Policy
PS C:\> Remove-WBBackupTarget -Policy $Policy -Target $BackupLocations[0]
```

This example removes a **WBBackupTarget** object from a **WBPolicy** object and then displays a list of backup locations left in the policy.

The first command gets the current backup policy and stores it in a variable named $Policy.

The second command gets the backup target locations and stores them in the variable named $BackupLocations.
The command also stores the backup policy in the variable named $Policy.

The third command removes the backup target in the first element of the $BackupLocations array from the policy stored in the $Policy variable.

## PARAMETERS

### -Policy
Specifies the **WBPolicy** object that contains the backup policy that this cmdlet updates.

```yaml
Type: WBPolicy
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Target
Specifies a backup target object that specifies the backup storage location to remove from the **WBPolicy** object.

```yaml
Type: WBBackupTarget
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Windows.ServerBackup.Commands.WBPolicy

### Microsoft.Windows.ServerBackup.Commands.WBBackupTarget

This cmdlet removes a **WBBackupTarget** object from a **WBPolicy** object that contains the backup policy.

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Add-WBBackupTarget](./Add-WBBackupTarget.md)

[Get-WBBackupTarget](./Get-WBBackupTarget.md)

[Get-WBPolicy](./Get-WBPolicy.md)

[New-WBBackupTarget](./New-WBBackupTarget.md)

