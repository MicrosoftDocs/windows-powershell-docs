---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/start-wbapplicationrecovery?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-WBApplicationRecovery
---

# Start-WBApplicationRecovery

## SYNOPSIS
Starts an application recovery operation.

## SYNTAX

```
Start-WBApplicationRecovery [-BackupSet] <WBBackupSet> [-ApplicationInBackup] <WBApplication>
 [[-RecoveryTarget] <String>] [-NoRollForward] [-Async] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Start-WBApplicationRecovery** cmdlet starts an application recovery operation.
To perform application recovery, you must specify the backup set from which to recover the application and the application to recover.
The application to recover must exist in the application array for the backup set specified.
If you do not specify a recovery target, the operation recovers the application to the application's original location.

## EXAMPLES

### Example 1: Start an application recovery operation
```
PS C:\> $Backup = Get-WBBackupSet
PS C:\> Start-WBApplicationRecovery -BackupSet $Backup -ApplicationInBackup $Backup.Application[0] -RecoveryTarget "F:\"
Warning
Start recovery of application Registry to F:\ ?
 [Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
Recovering component Registry :
Recovering component Registry : Preparing to recover.
Completed.
```

This example recovers an application to a file path.

The first command gets the backup object from the system catalog and stores it in the variable named $Backup.

The second command starts the recovery by specifying $Backup as the backup set, and specifying the first element of the application array within the backup set.
The first element of the application array is the registry.

## PARAMETERS

### -ApplicationInBackup
Specifies an application object that contains the application that this cmdlet recovers.
This application must exist in the backup set's application array.

```yaml
Type: WBApplication
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Async
Indicates that Windows PowerShell returns immediately after starting the backup without displaying status messages to the console.

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

### -BackupSet
Specifies a backup set object that contains the backup set from which to recover the application.

```yaml
Type: WBBackupSet
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoRollForward
Indicates that this cmdlet recovers applications from a previous point in time if you select the latest version of the application from the backups.
For versions of the application other than the latest version, the operation uses point-in-time recovery by default.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryTarget
Specifies the path to which the recovery operation recovers the application.

```yaml
Type: String
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

### Microsoft.Windows.ServerBackup.Commands.WBBackupSet

### Microsoft.Windows.ServerBackup.Commands.WBApplication

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-WBBackupSet](./Get-WBBackupSet.md)

