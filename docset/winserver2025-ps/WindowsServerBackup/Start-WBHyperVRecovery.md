---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/start-wbhypervrecovery?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-WBHyperVRecovery
---

# Start-WBHyperVRecovery

## SYNOPSIS
Starts recovery of a Hyper-V Server 2016 virtual machine.

## SYNTAX

```
Start-WBHyperVRecovery [-BackupSet] <WBBackupSet> [-VMInBackup] <WBVirtualMachine[]> [[-TargetPath] <String>]
 [-NoRollForward] [-Async] [-Force] [-UseAlternateLocation] [-RecreatePath] [<CommonParameters>]
```

## DESCRIPTION
The **Start-WBHyperVRecovery** cmdlet starts a recovery operation for a Hyper-V virtual machine.
Use the application array from a **WBBackupSet** object to specify the virtual machines that you want to recover.

For an overview of Hyper-V, see [Hyper-V Overview](https://technet.microsoft.com/en-us/library/hh831531.aspx) on TechNet.


## EXAMPLES

### Example 1: Recover a virtual machine to its original location
```
PS C:\> $Backup = Get-WBBackupSet
PS C:\> Start-WBHyperVRecovery -BackupSet $Backup -VMInBackup $Backup.Application[0].Component[0]
```

This example recovers a virtual machine to its original location.

The first command gets the backup set object from the system catalog and stores it in the variable named $Backup.

The second command uses the backup set stored in $Backup to recover a virtual machine that has the ID 285CEA9B-E337-44E1-9BF9-BF431BC3EB35 to its original location.

### Example 2: Recover a virtual machine to an alternate location
```
PS C:\> $Backup = Get-WBBackupSet
PS C:\> Start-WBHyperVRecovery -BackupSet $Backup -VMInBackup $Backup.Application[0].Component[1] -TargetPath "F:\Dir1" -UseAlternateLocation -RecreatePath
```

This example recovers a virtual machine to an alternate location.

The first command gets the backup set object from the system catalog and stores it in the variable named $Backup.

The second command recovers the virtual machine that has the ID F7D8AAF4-D086-47CC-8264-61F80527BFF4 to an alternate location.

## PARAMETERS

### -Async
Indicates that Windows PowerShell returns immediately after it starts the recovery and does not display status messages.

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
Specifies a backup set object that contains a Hyper-V application backup.

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
Indicates that this cmdlet recovers a virtual machine from a previous point in time if you select the latest version of the application from the backups.
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

### -RecreatePath
Indicates that the recovery operation recreates the original folder structure when it restores a virtual machine.
This option applies only if you recover a virtual machine to an alternate location.
If you do not specify this option, the recovery puts all files for a component under a single folder.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetPath
Specifies an alternate location in the backup set where the recovery process searches for files.

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

### -UseAlternateLocation
Indicates that you can use the recovery process to recover Hyper-V components, update configuration, and register the virtual machine with the Hyper-V management service.
This option applies only if you recover a virtual machine to an alternate location.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMInBackup
Specifies a list of virtual machine objects that contain the virtual machines to recover.
This list must contain virtual machines from the Hyper-V application object in the backup set's application array.

```yaml
Type: WBVirtualMachine[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Windows.ServerBackup.Commands.WBBackupSet

### Microsoft.Windows.ServerBackup.Commands.WBVirtualMachine[]

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[HyperV Overview](https://technet.microsoft.com/en-us/library/hh831531.aspx)

[Get-WBBackupSet](./Get-WBBackupSet.md)

