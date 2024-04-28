---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/start-wbbackup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-WBBackup
---

# Start-WBBackup

## SYNOPSIS
Starts a one-time backup operation.

## SYNTAX

```
Start-WBBackup [-Policy] <WBPolicy> [-Async] [-Force] [-AllowDeleteOldBackups] [-DoNotVerifyMedia]
 [<CommonParameters>]
```

## DESCRIPTION
The **Start-WBBackup** cmdlet starts a one-time backup operation.

You can use the settings from an existing backup policy for the scheduled backup by specifying a **WBPolicy** object, or you can start a backup by using new settings.
If you use new settings to create a backup, you must do the following:

- Specify the items to include in the backup by using the [Add-WBVolume](./Add-WBVolume.md), [Add-WBFileSpec](./Add-WBFileSpec.md), [Add-WBSystemState](./Add-WBSystemState.md), and [Add-WBBareMetalRecovery](./Add-WBBareMetalRecovery.md) cmdlets.
- Specify the location for backup storage by using the locations already defined in a **WBBackupTarget** object or by updating an object of that type.

Before you can add a backup target to a **WBPolicy** object, put the **WBPolicy** object in edit mode.
To put the **WBPolicy** object in edit mode for a policy that you have set as the scheduled backup policy, use the Get-WBPolicy cmdlet with the *Editable* parameter.
The [Get-WBPolicy](./Get-WBPolicy.md) cmdlet creates a new **WBPolicy** object that is already in edit mode.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Start a backup by using new settings
```
The first command creates a new backup policy object and stores it in a variable named $Policy.
PS C:\> $Policy = New-WBPolicy

The next command creates a backup source, adds the file named C:\15-12-08_1645.jpg to the backup source, and stores the backup source in a variable named $FileSpec.
PS C:\> $FileSpec = New-WBFileSpec -FileSpec "C:\15-12-08_1645.jpg"

This command associates the backup source in the $FileSpec variable with the backup policy in the $Policy variable.
PS C:\> Add-WBFileSpec -Policy $Policy -FileSpec $FileSpec

This command stores the volume that has the drive letter F: in the variable named $Volume.
PS C:\> $Volume = Get-WBVolume -VolumePath "F:"

This command stores the volume in the $Volume variable in the backup policy in the $Policy variable.
PS C:\> Add-WBVolume -Policy $Policy -Volume $Volume

This command adds the current system state options to the backup policy in the $Policy variable.
PS C:\> Add-WBSystemState $Policy

This command adds the ability to perform a bare-metal recovery to the backup policy in the $Policy variable.
PS C:\> Add-WBBareMetalRecovery $Policy

This command creates a new backup location object that contains the volume that has the drive letter D: and then stores that object in the $BackupLocation variable.
PS C:\> $BackupLocation = New-WBBackupTarget -VolumePath "D:"

This command adds the backup target based on the backup policy in the $Policy variable and the backup location in the $BackupLocation variable.
PS C:\> Add-WBBackupTarget -Policy $Policy -Target $BackupLocation

This command specifies that the backup policy in the $Policy variable uses Volume Shadow Copy Service (VSS) copy backups.
PS C:\> Set-WBVssBackupOptions -Policy $Policy -VssCopyBackup

This command starts the backup by using the backup policy in the $Policy variable.
PS C:\> Start-WBBackup -Policy $Policy
```

This example starts a backup by using new settings.

### Example 2: Start a backup by using backup policy settings
```
PS C:\> $Policy = Get-WBPolicy
PS C:\> Start-WBBackup -Policy $Policy -Async
PS C:\> $BackupJob = Get-WBJob
```

This example starts a backup by using the settings for scheduled backups defined in a backup policy.

The first command gets the current backup policy and stores it in the variable named $Policy.

The second command starts the backup.
Because the command specifies the *Async* parameter, the cmdlet returns immediately.

The third command gets the backup status and stores it in the variable named $BackupJob.
Because the second command includes the *Async*  parameter, you can view the backup status by using the Get-WBJob cmdlet.

## PARAMETERS

### -AllowDeleteOldBackups
Indicates that the cmdlet deletes backups of older versions of the operating system.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Async
Indicates that Windows PowerShell returns immediately after the backup starts and does not display status messages.
If you specify this parameter and choose not to display status messages, you can use the Get-WBJob cmdlet to get the status of the currently running backup operation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DoNotVerifyMedia
Do not use.
This parameter is not implemented in this version of the module.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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
Specifies a **WBPolicy** object that includes the policy settings for the backup by using an existing backup policy object.

```yaml
Type: WBPolicy
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Windows.ServerBackup.Commands.WBPolicy

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Add-WBBackupTarget](./Add-WBBackupTarget.md)

[Add-WBBareMetalRecovery](./Add-WBBareMetalRecovery.md)

[Add-WBFileSpec](./Add-WBFileSpec.md)

[Add-WBSystemState](./Add-WBSystemState.md)

[Add-WBVolume](./Add-WBVolume.md)

[Get-WBJob](./Get-WBJob.md)

[Get-WBPolicy](./Get-WBPolicy.md)

[Get-WBVolume](./Get-WBVolume.md)

[New-WBBackupTarget](./New-WBBackupTarget.md)

[New-WBFileSpec](./New-WBFileSpec.md)

[New-WBPolicy](./New-WBPolicy.md)

[Resume-WBBackup](./Resume-WBBackup.md)

[Set-WBVssBackupOption](./Set-WBVssBackupOption.md)

