---
author: Kateyanne
external help file: WSBackup_Cmdlets.xml
manager: dansimp
Module Name: WindowsServerBackup
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/windowsserverbackup/get-wbperformanceconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WBPerformanceConfiguration

## SYNOPSIS
Retrieves the current volume backup performance settings.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-WBPerformanceConfiguration [-OverallPerformanceSetting]
```

### UNNAMED_PARAMETER_SET_2
```
Get-WBPerformanceConfiguration [-Volume] <WBVolume>
```

## DESCRIPTION
The **Get-WBPerformanceSetting** cmdlet retrieves the current performance settings for volume backups.
The settings are applicable only for volume backups; these settings are not applicable for files, folders, system state, or applications.
The settings apply globally to all volumes in a backup, or to specific volumes.
The valid settings are: 

- AlwaysFull:  The time to create a backup is proportional to the size of volume being backed up.
This setting applies at a global level for all volumes or for specific volumes. 

- AlwaysIncremental:  Increase the backup speed by just tracking the changes between the last and current backup.
This option is not recommended for servers with disk-intensive operation which may experience reduced disk throughput on volumes included in the backup.
This can be set at a global level for all volumes or specific for some volumes. 

- Custom:  This is the global setting reported in case there is a specific volume level setting set.

## EXAMPLES

### Example 1:Retrieve global settings
```
PS C:\> Get-WBPerformanceSetting -OverallPerformanceSetting AlwaysIncremental
```

This example retrieves the global settings for all volumes with the AlwaysIncremental setting.

### Example 2: Retrieve settings for a volume
```
PS C:\>$Backup = Get-WBBackupSet PS C:\> Get-WBPerformanceSetting -Volume $Backup.Volume[1] AlwaysFull
```

This example retrieves the settings for a specific volume with the AlwaysFull setting.

## PARAMETERS

### -OverallPerformanceSetting
If specified, indicates that the returned data is to be for the global setting.

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

### -Volume
Specifies the **WBVolume** object for which the current performance settings are retrieved.

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
Indicates either global settings or volume settings.

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-WBPerformanceConfiguration](./Set-WBPerformanceConfiguration.md)



