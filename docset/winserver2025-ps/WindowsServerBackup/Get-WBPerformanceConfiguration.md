---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/get-wbperformanceconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WBPerformanceConfiguration
---

# Get-WBPerformanceConfiguration

## SYNOPSIS
Gets the current volume backup performance settings.

## SYNTAX

### Volume
```
Get-WBPerformanceConfiguration [-Volume] <WBVolume> [<CommonParameters>]
```

### OverallSetting
```
Get-WBPerformanceConfiguration [-OverallPerformanceSetting] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WBPerformanceConfiguration** cmdlet gets the current performance settings for volume backups.
The settings are applicable only for volume backups; these settings are not applicable for files, folders, system state, or applications.
The settings apply globally to all volumes in a backup, or to specific volumes.
The acceptable values for this parameter are:

- AlwaysFull: The time to create a backup is proportional to the size of volume being backed up.
This setting applies at a global level for all volumes or for specific volumes.

- AlwaysIncremental: Increase the backup speed by just tracking the changes between the last and current backup.
This option is not recommended for servers with disk-intensive operation which may experience reduced disk throughput on volumes included in the backup.
This can be set at a global level for all volumes or specific for some volumes.

- Custom: This is the global setting reported in case there is a specific volume level setting set.

## EXAMPLES

### Example 1: Get global settings
```
PS C:\> Get-WBPerformanceConfiguration -OverallPerformanceSetting AlwaysIncremental
```

This command gets the global settings for all volumes with the AlwaysIncremental setting.

### Example 2: Get settings for a volume
```
PS C:\> $Backup = Get-WBBackupSet
PS C:\> Get-WBPerformanceConfiguration -Volume $Backup.Volume[1] AlwaysFull
```

This example gets the settings for a specific volume with the AlwaysFull setting.

The first command gets the backup set from the local machine and stores the result in the variable named $Backup.

The second command gets the settings from the volume at index 1 that is stored in the $Backup variable.

## PARAMETERS

### -OverallPerformanceSetting
Indicates that the returned data is used for the global setting.

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

### -Volume
Specifies the **WBVolume** object for which this cmdlet gets the current performance settings.

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

[Get-WBBackupSet](./Get-WBBackupSet.md)

[Set-WBPerformanceConfiguration](./Set-WBPerformanceConfiguration.md)

