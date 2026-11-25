---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/set-wbvssbackupoption?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WBVssBackupOption
---

# Set-WBVssBackupOption

## SYNOPSIS
Sets a value that determines the VSS setting in the backup policy.

## SYNTAX

```
Set-WBVssBackupOption [-Policy] <WBPolicy> [-VssCopyBackup] [-VssFullBackup] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WBVssBackupOption** cmdlet sets a value that determines whether the backups created through the **WBPolicy** object are Volume Shadow Copy Service (VSS) copy backups or VSS full backups.

Create VSS full backups if you are not using any other product to back up applications.
This option updates the backup history of each file and deletes the application log files.
Create VSS copy backups if you are using another product to back up applications that are on the volumes included in the backup.
This option retains the application log files.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Set the VSS backup policy
```
PS C:\> $Policy = Get-WBPolicy
PS C:\> Set-WBVssBackupOption -Policy $Policy -VssFullBackup
```

This example sets the backup policy to create backups that are VSS full backups.

The first command stores the result of the **Get-WBPolicy** cmdlet in the variable named $Policy.

The second command sets the VSS setting for the backup policy in the $Policy variable.

## PARAMETERS

### -Policy
Specifies the **WBPolicy** object to update.

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

### -VssCopyBackup
Indicates that the backups in the backup policy are VSS copy backups.

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

### -VssFullBackup
Indicates that the backups in the backup policy are VSS full backups.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Windows.ServerBackup.Commands.WBPolicy

## OUTPUTS

### System.Object

## NOTES
* The **WBPolicy** object must be in edit mode. To put the **WBPolicy** object in edit mode for a policy that you set as the scheduled backup policy, use the [New-WBPolicy](./New-WBPolicy.md) cmdlet with the *Editable* parameter. The **New-WBPolicy** cmdlet creates a new **WBPolicy** object that is already in edit mode.

## RELATED LINKS

[Get-WBVssBackupOption](./Get-WBVssBackupOption.md)

