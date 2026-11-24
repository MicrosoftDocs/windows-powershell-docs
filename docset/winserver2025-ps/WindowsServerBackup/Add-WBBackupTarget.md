---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/add-wbbackuptarget?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WBBackupTarget
---

# Add-WBBackupTarget

## SYNOPSIS
Adds a backup target to a backup policy.

## SYNTAX

```
Add-WBBackupTarget [-Policy] <WBPolicy> [-Target] <WBBackupTarget> [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Add-WBBackupTarget** cmdlet adds a **WBBackupTarget** object, which specifies backup storage locations, to a **WBPolicy** object that contains a backup policy.
To use this cmdlet, you must first use the New-WBBackupTarget cmdlet to create a **WBBackupTarget** object.
You can then use the Add-WBBackupTarget cmdlet to specify the storage location by using a disk, a volume, or a remote shared folder (network) location.

Before you can add a backup target to a **WBPolicy** object, you must make sure that the **WBPolicy** object is in edit mode.
To put the **WBPolicy** object in edit mode for a policy that you have set as the scheduled backup policy, use the [Get-WBPolicy](./Get-WBPolicy.md) cmdlet with the *Editable* parameter.
The [New-WBPolicy](./New-WBPolicy.md) cmdlet creates a new **WBPolicy** object that is already in edit mode.

If you specify a disk as a storage location for backups, the server formats the disk before it uses the disk and permanently deletes any existing data on the disk.

You can add only one storage type at a time to a policy.
If you specify a shared folder as the storage location, you cannot add more locations because you can specify only one shared folder as a storage location at any time.
However, you can specify multiple disks or volumes at one time by calling [Add-WBBackupTarget](./Add-WBBackupTarget.md) for each location.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Add a backup storage location to a backup policy
```
PS C:\> $Policy = Get-WBPolicy
PS C:\> Add-WBBackupTarget -Policy $Policy -Target $BackupLocation
```

This example adds a backup storage location to a backup policy.

The first command gets the current backup policy and stores it in a variable named $Policy.

The second command adds the backup storage location in the variable named $BackupLocation to the **WBPolicy** object in the variable named $Policy.
You can create the backup target that you add to the location in the $BackupLocation variable by using the [New-WBBackupTarget](./New-WBBackupTarget.md) cmdlet.

## PARAMETERS

### -Force
Indicates that the cmdlet adds the backup target without prompting you for confirmation.
By default, the cmdlet prompts you for confirmation before it proceeds.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Policy
Specifies a backup policy object that contains the backup policy to update.

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
Specifies a backup target object that contains the backup storage location to add to the backup policy.

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

This cmdlet adds a **WBBackupTarget** object, which contains new backup storage locations, to a **WBPolicy** object that contains a backup policy.
To add more than one storage location, you must call the **Add-WBBackupTarget** cmdlet separately for each location.

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

[Get-WBBackupTarget](./Get-WBBackupTarget.md)

[Get-WBPolicy](./Get-WBPolicy.md)

[New-WBBackupTarget](./New-WBBackupTarget.md)

[New-WBPolicy](./New-WBPolicy.md)

[Remove-WBBackupTarget](./Remove-WBBackupTarget.md)

