---
external help file: WSBackup_Cmdlets.xml
Module Name: WindowsServerBackup
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/start-wbhypervrecovery?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Start-WBHyperVRecovery

## SYNOPSIS
Starts recovery of a hv_win8_2 virtual machine.

## SYNTAX

```
Start-WBHyperVRecovery [-BackupSet] <WBBackupSet> [-VMInBackup] <WBVirtualMachine[]> [[-TargetPath] <String>]
 [-NoRollForward] [-Async] [-Force] [-UseAlternateLocation] [-RecreatePath]
```

## DESCRIPTION
The **Start-WBHyperVRecovery** cmdlet starts a recovery operation for a hv_win8_1 virtual machine (VM).
Use the application array from a **WBBackupSet** object to specify the VMs that you want to recover.

For an overview of hv_win8_2, see HyperV Overviewhttp://technet.microsoft.com/en-us/library/hh831531.aspx (http://technet.microsoft.com/en-us/library/hh831531.aspx) on TechNet.

## EXAMPLES

### Example 1: Recover a VM to its original location
```
PS C:\>$Backup = Get-WBBackupSet PS C:\> Start-WBHyperVRecovery -BackupSet $Backup -VMInBackup $Backup.Application[0].Component[0]

WARNING: The virtual machines may not start if the network settings are
different after recovery. Verify the settings of the virtual machines using
HyperV Manager before attempting to start.

Warning
Start recovery of application HyperV to original location ?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
Recovering component 285CEA9B-E337-44E1-9BF9-BF431BC3EB35 :
Application recovery in progress.
Completed.
```

This example recovers a VM to its original location.

The first command gets the backup set object from the system catalog and stores it in the variable named **$Backup**.

The second command uses the backup set stored in **$Backup** to recover a VM that has the ID 285CEA9B-E337-44E1-9BF9-BF431BC3EB35 to its original location.

### Example 2: Recover a VM to an alternate location
```
PS C:\>$Backup = Get-WBBackupSet PS C:\> Start-WBHyperVRecovery -BackupSet $Backup -VMInBackup $Backup.Application[0].Component[1] -RecoveryTarget F:\Dir1 -AlternateLocation -RecreatePath

WARNING: The virtual machines may not start if the network settings are
different after recovery. Verify the settings of the virtual machines using
HyperV manager before attempting to start.
WARNING: If a virtual machine you are trying to recover to alternate location
was backed up from this host, this will delete and overwrite the original
virtual machine if it still exists.

Warning
Start recovery of application HyperV to F:\dir1 ?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
Recovering component F7D8AAF4-D086-47CC-8264-61F80527BFF4 :
Recovering component F7D8AAF4-D086-47CC-8264-61F80527BFF4 : Preparing to recover.
Completed.
```

This example recovers a VM to an alternate location.

The first command gets the backup set object from the system catalog and stores it in the variable named **$Backup**.

The second command recovers the VM that has the ID F7D8AAF4-D086-47CC-8264-61F80527BFF4 to an alternate location.

## PARAMETERS

### -Async
Indicates that Windows PowerShell® returns immediately after it starts the recovery and does not display status messages.

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

### -BackupSet
Specifies a backup set object that contains a hv_win8_2 application backup.

```yaml
Type: WBBackupSet
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Force
Indicates that the cmdlet starts the recovery operation without prompting you for confirmation.
By default, the cmdlet prompts you for confirmation before it proceeds.

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

### -NoRollForward
Indicates that you can recover a VM from a previous point in time if you select the latest version of the application from the backups.
For versions of the application other than the latest version, the operation uses point-in-time recovery by default.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecreatePath
Indicates that the recovery operation recreates the original folder structure when it restores a VM.
This option applies only if you recover a VM to an alternate location.
If you do not specify this option, the recovery puts all files for a component under a single folder.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 8
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
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseAlternateLocation
Indicates that you can use the recovery process to recover hv_win8_2 components, update configuration, and register the VM with the hv_win8_2 management service.
This option applies only if you recover a VM to an alternate location.

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

### -VMInBackup
Specifies a list of virtual machine objects that contain the VMs to recover.
This list must contain VMs from the hv_win8_2 application object in the backup set's application array.

```yaml
Type: WBVirtualMachine[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

### WBBackupSet, WBVirtualMachine

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS



[Get-WBBackupSet](./Get-WBBackupSet.md)

