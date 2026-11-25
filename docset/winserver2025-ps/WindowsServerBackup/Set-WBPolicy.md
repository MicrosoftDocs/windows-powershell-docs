---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/set-wbpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WBPolicy
---

# Set-WBPolicy

## SYNOPSIS
Sets the backup policy for scheduled backups.

## SYNTAX

```
Set-WBPolicy [-Policy] <WBPolicy> [-Force] [-AllowDeleteOldBackups] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WBPolicy** cmdlet sets a **WBPolicy** object as the backup policy for scheduled backups.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Set a backup policy
```
The first command creates a backup policy object and stores it in the $Policy variable.
PS C:\> $Policy = New-WBPolicy

The second command creates a file specification object and stores the result in the $FileSpec variable. A file specification determines what items to include or exclude from backups.
PS C:\> $FileSpec = New-WBFileSpec -FileSpec "C:\dir1"

The third command adds a Windows Backup file specification to the backup policy.
PS C:\> Add-WBFileSpec -Policy $Policy -FileSpec $FileSpec

The fourth command adds bare metal recovery to the policy.
PS C:\> Add-WBBareMetalRecovery $Policy

The fifth command gets the Windows Backup disk configuration. This cmdlet gets the list of internal and external disks available for the local computer and stores the resulting list in the $Disks variable.
PS C:\> $Disks = Get-WBDisk

The sixth command creates a backup target object and stores it in the $BackupLocation variable.
PS C:\> $BackupLocation = New-WBBackupTarget -Disk $Disks[2]

The seventh command adds a backup target. The $BackupLocation variable specifies the backup locations in the policy.
PS C:\> Add-WBBackupTarget -Editable -Policy $Policy -Target $BackupLocation

The eighth command sets the backup schedule in the policy. The cmdlet sets the times to create daily backups.
PS C:\> Set-WBSchedule -Policy $Policy 09:00

The ninth command sets the backup policy object for the computer.
PS C:\> Set-WBPolicy -Policy $Policy
```

This example sets a new backup policy.

### Example 2: Set backup policy by using a remote shared file
```
The first command gets the backup policy object and stores it in the $Policy variable.
PS C:\> $Policy = Get-WBPolicy -Editable

The second command creates a backup target object and stores it in the $BackupLocation variable. When you are prompted, specify the credentials to access the remote shared folder and acknowledge the warning about choosing a remote shared folder as a backup storage location.
PS C:\> $BackupLocation = New-WBBackupTarget -NetworkPath "\\ContosoSrv\ContosoShared"

The third command adds a backup target to the policy. The target is the $BackupLocation variable.
PS C:\> Add-WBBackupTarget -Policy $policy -Target $BackupLocation

The fourth command sets backup policy object from the changes to the $Policy variable.
PS C:\> Set-WBPolicy -Policy $Policy
```

This example modifies the backup policy for the set **WBPolicy** object and changes the backup location to a remote file share.

## PARAMETERS

### -AllowDeleteOldBackups
Indicates whether new backups can overwrite older backups.

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

### -Policy
Specifies a **WBPolicy** object that contains that contains a backup policy that this cmdlet updates.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Windows.ServerBackup.Commands.WBPolicy

## OUTPUTS

### System.Object

## NOTES
* The **WBPolicy** object must be in edit mode. To put the **WBPolicy** object in edit mode for a policy that is set as the scheduled backup policy, use the Get-WBPolicy cmdlet with the *Editable* parameter. The New-WBPolicy cmdlet creates a **WBPolicy** object in edit mode.

## RELATED LINKS

[Get-WBPolicy](./Get-WBPolicy.md)

[New-WBPolicy](./New-WBPolicy.md)

[Remove-WBPolicy](./Remove-WBPolicy.md)

