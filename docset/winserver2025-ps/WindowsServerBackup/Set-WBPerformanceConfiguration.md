---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/set-wbperformanceconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WBPerformanceConfiguration
---

# Set-WBPerformanceConfiguration

## SYNOPSIS
Sets the current volume backup performance settings.

## SYNTAX

### Volume
```
Set-WBPerformanceConfiguration [-Volume] <WBVolume> [-PerformanceSetting] <WBPerformanceConfiguration>
 [<CommonParameters>]
```

### OverallSetting
```
Set-WBPerformanceConfiguration [-OverallPerformanceSetting] [-PerformanceSetting] <WBPerformanceConfiguration>
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-WBPerformanceSetting** cmdlet sets the current volume backup performance settings.
The settings are applicable only for volume backups; these settings are not applicable for files, folders, system state, or applications.
The settings apply globally to all volumes in a backup, or to specific volumes.

## EXAMPLES

### Example 1: Set the global performance setting
```
PS C:\> Set-WBPerformanceConfiguration -OverallPerformanceSetting AlwaysIncremental
```

This command sets the global performance settings as incremental for volume backups.

### Example 2: Set a specific volume performance setting
```
PS C:\> $Backup = Get-WBBackupSet
PS C:\> Set-WBPerformanceConfiguration -Volume $Backup.Volume[1] AlwaysFull
```

This example sets the performance settings for a specific volume.

The first command stores the result of the [Get-WBBackupSet](./Get-WBBackupSet.md) cmdlet in the variable named $Backup.

The second command sets the **AlwaysFull** performance setting on the second volume of $Backup.

## PARAMETERS

### -OverallPerformanceSetting
Indicates that the changes affect the global performance setting.
If you do not use this parameter, then the *Volume* parameter must be specified.

```yaml
Type: SwitchParameter
Parameter Sets: OverallSetting
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PerformanceSetting
Specifies the performance settings for which this cmdlet sets.
The acceptable values for this parameter are::

- **AlwaysFull**: The time to create a backup is proportional to the size of volume being backed up.
This can be set at a global level for all volumes or specific for some volumes.
- **AlwaysIncremental**: Increase the backup speed by just tracking the changes between the last and current backup.
This option is not recommended for servers with disk-intensive operation which may experience reduced disk throughput on volumes included in the backup.
This can be set at a global level for all volumes or specific for some volumes.

```yaml
Type: WBPerformanceConfiguration
Parameter Sets: (All)
Aliases:
Accepted values: AlwaysFull, AlwaysIncremental, Custom

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Volume
Specifies the object for which this cmdlet sets the current performance settings.

```yaml
Type: WBVolume
Parameter Sets: Volume
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-WBPerformanceConfiguration](./Get-WBPerformanceConfiguration.md)

