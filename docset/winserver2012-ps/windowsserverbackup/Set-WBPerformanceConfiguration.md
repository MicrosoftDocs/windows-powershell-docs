---
external help file: WSBackup_Cmdlets.xml
Module Name: WindowsServerBackup
online version: https://docs.microsoft.com/powershell/module/windowsserverbackup/set-wbperformanceconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-WBPerformanceConfiguration

## SYNOPSIS
Sets the current volume backup performance settings.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-WBPerformanceConfiguration [-OverallPerformanceSetting] [-PerformanceSetting] <WBPerformanceConfiguration>
```

### UNNAMED_PARAMETER_SET_2
```
Set-WBPerformanceConfiguration [-Volume] <WBVolume> [-PerformanceSetting] <WBPerformanceConfiguration>
```

## DESCRIPTION
The **Set-WBPerformanceSetting** cmdlet sets the current volume backup performance settings.
The settings are applicable only for volume backups; these settings are not applicable for files, folders, system state, or applications.
The settings apply globally to all volumes in a backup, or to specific volumes.

## EXAMPLES

### Example 1: Set the global performance setting
```
PS C:\> Set-WBPerformanceSetting -OverallPerformanceSetting AlwaysIncremental
```

This command sets the global performance settings as incremental for volume backups.

### Example 2: Set a specific volume performance setting
```
PS C:\>$Backup = Get-WBBackupSet PS C:\> Set-WBPerformanceSetting -Volume $Backup.Volume[1] AlwaysFull
```

This example sets the performance settings for a specific volume.

The first command stores the result of the Get-WBBackupSet cmdlet in the variable named **$Backup**.

The second command sets the **AlwaysFull** performance setting on the second volume of **$Backup**.

## PARAMETERS

### -OverallPerformanceSetting
If present, specifies that the changes affect the global performance setting.
If not present, then the **Volume** parameter must be specified.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PerformanceSetting
The valid settings are:

--**AlwaysFull**:  The time to create a backup is proportional to the size of volume being backed up.
This can be set at a global level for all volumes or specific for some volumes.

--**AlwaysIncremental**:  Increase the backup speed by just tracking the changes between the last and current backup.
This option is not recommended for servers with disk-intensive operation which may experience reduced disk throughput on volumes included in the backup.
This can be set at a global level for all volumes or specific for some volumes.

```yaml
Type: WBPerformanceConfiguration
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Volume
Specifies the object for the current performance settings.

```yaml
Type: WBVolume
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### SwitchParameter, WBVolume
Indicates either a global setting or the per volume performance setting.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-WBPerformanceConfiguration](./Get-WBPerformanceConfiguration.md)



