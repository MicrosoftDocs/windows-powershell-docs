---
external help file: WSBackup_Cmdlets.xml
Module Name: WindowsServerBackup
online version: https://docs.microsoft.com/powershell/module/windowsserverbackup/start-wbvolumerecovery?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Start-WBVolumeRecovery

## SYNOPSIS
Starts a volume recovery operation.

## SYNTAX

```
Start-WBVolumeRecovery [-BackupSet] <WBBackupSet> [-VolumeInBackup] <WBVolume>
 [[-RecoveryTargetVolume] <WBVolume>] [-SkipBadClusterCheck] [-Async] [-Force]
```

## DESCRIPTION
The **Start-WBVolumeRecovery** cmdlet starts a volume recovery operation from a **WBBackupSet** backup.
The operation formats the recovery target volume before recovery.

## EXAMPLES

### Example 1: Start volume recovery
```
PS C:\>$Backup = Get-WBBackupSet PS C:\> Start-WBVolumeRecovery -BackupSet $Backup -VolumeInBackup $Backup.Volume[0] -Force
```

This example starts a volume recovery to the original location, and it uses the **Force** parameter to perform the operation without a confirmation message.

The first command stores the result of the Get-WBBackupSet cmdlet  in the variable named **$Backup**.
The object stored in the variable is a **WBBackupSet** object.

The second command starts the volume recovery by using the **$Backup** variable as input, specifying the first item in the volume array in the **WBBackupSet** object.

### Example 2: Start a volume recovery with a recovery target
```
PS C:\>$Backup = Get-WBBackupSet PS C:\>$RecoveryTarget = Get-WBVolume PS C:\> Start-WBVolumeRecovery -BackupSet $Backup -VolumeInBackup $Backup.Volume[0] -RecoveryTargetVolume $RecoveryTarget
```

This example starts volume recovery for the System Reserved volume and restores to the recovery target volume.

The first command stores the output of the Get-WBBackupSet cmdlet in the variable named **$Backup**.

The second command stores the output of the Get-WBVolume cmdlet in the variable named **$RecoveryTarget**.

The third command starts the recovery operation for the volume specifying the **$Backup** variable as the backup to use and the **$RecoveryTarget** variable as the volume to restore.

## PARAMETERS

### -Async
Indicates that Windows PowerShell returns immediately after it starts the operation.
The cmdlet does not display status information.

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
Specifies a **WBBackupSet** object that contains the backup set for the volume recovery operation.

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
Performs the recovery operation without requesting confirmation.
By default, the cmdlet prompts you for confirmation.

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

### -RecoveryTargetVolume
Specifies a **WBVolume** object that contains the recovery target volume.
If you do not specify a recovery target volume, the original volume is the recovery target volume.
The recovery operation formats the volume before recovery.

```yaml
Type: WBVolume
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipBadClusterCheck
Indicates that the system not perform bad cluster checks.

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

### -VolumeInBackup
Specifies a WBVolume object that contains the source volume to recover.
The **WBBackupSet** object returned by the **BackupSet** parameter contains the **WBVolume** information.

```yaml
Type: WBVolume
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

### WBBackupSet, WBVolume, WBVolume

## OUTPUTS

### System.String
If you do not specify the **Async** parameter, the status of the recovery operation displays at periodic intervals until the recovery operation finishes.
You can also use the Get-WBJob cmdlet to get the status of the current recovery operation.
Type  `Get-WBJob -Previous 1` to get the status after the recovery operation completes.

## NOTES

## RELATED LINKS

[Resume-WBVolumeRecovery](./Resume-WBVolumeRecovery.md)

