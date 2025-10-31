---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/start-wbsystemstaterecovery?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-WBSystemStateRecovery
---

# Start-WBSystemStateRecovery

## SYNOPSIS
Starts a system state recovery operation.

## SYNTAX

### SSR (Default)
```
Start-WBSystemStateRecovery [-BackupSet] <WBBackupSet> [[-TargetPath] <String>] [-AuthoritativeSysvolRecovery]
 [-RestartComputer] [-Async] [-Force] [<CommonParameters>]
```

### ADIFM
```
Start-WBSystemStateRecovery [-BackupSet] <WBBackupSet> [-ADIFM] [-TargetPath] <String> [-Async] [-Force]
 [<CommonParameters>]
```

## DESCRIPTION
The **Start-WBSystemStateRecovery** cmdlet starts a system state recovery operation.
If the System State recovery operation is performed on the actual computer, completion of the operation requires a restart.
If recovery is performed on an Active Directory (AD) computer, this cmdlet must be run in Directory Services Restore Mode (DSRM).

## EXAMPLES

### Example 1: Start a system state recovery operation
```
PS C:\> $Backup = Get-WBBackupSet
PS C:\> Start-WBSystemStateRecovery -BackupSet $Backup -Force -RestartComputer -Async
```

This example starts a system state recovery operation, and then restarts the computer at the end of the recovery operation.

The first command stores the result of [Get-WBBackupSet](./Get-WBBackupSet.md) in a variable named $Backup.

The second command starts the system state recovery from the backup stored in the $Backup variable.
The command also uses the *Force* parameter to perform the recovery without prompting, the *RestartComputer* parameter to restart the computer when recovery finishes, and the *Async* parameter to suppress status output.

## PARAMETERS

### -ADIFM
Indicates that this cmdlet recovers all the related data needed for Active Directory Domain Services from an install from a media (IFM) operation.
Active Directory Install From Media (ADIFM) creates a copy of the Active Directory database, registry, and SYSVOL state, and then saves this information in the location specified by the *RecoveryTarget* parameter.
Use this parameter only when *RecoveryTarget* is specified.
This parameter is valid only if the backup set contains an Active Directory system state backup.

```yaml
Type: SwitchParameter
Parameter Sets: ADIFM
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Async
Indicates that Windows PowerShell returns immediately after starting the backup, and does not output status to the screen.

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

### -AuthoritativeSysvolRecovery
Indicates that this cmdlet performs an authoritative recovery of SYSVOL, the System Volume shared directory.
This parameter is valid only if the backup set contains an Active Directory system state backup.

```yaml
Type: SwitchParameter
Parameter Sets: SSR
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackupSet
Specifies the backup set from which this cmdlet performs system state recovery.

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

### -RestartComputer
Indicates that this cmdlet performs a system restart at the completion of the system state recovery operation.
Use this parameter only for a recovery to the original location.
Do not use this parameter if you need to perform steps after the recovery operation.

```yaml
Type: SwitchParameter
Parameter Sets: SSR
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetPath
Specifies an alternate location where the files belonging to system state can be recovered from the backup set.
If you do not specify this parameter, system state recovery is performed for the actual computer, which needs a restart at the end of the operation.
ADIFM recovery requires this parameter.

```yaml
Type: String
Parameter Sets: SSR
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ADIFM
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Windows.ServerBackup.Commands.WBBackupSet

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-WBBackupSet](./Get-WBBackupSet.md)

[Get-WBJob](./Get-WBJob.md)

