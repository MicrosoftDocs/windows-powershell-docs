---
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
online version: 
schema: 2.0.0
title: Get-WBPerformanceConfiguration
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 7046A80C-3AF8-4F11-9551-40D8D617DA77
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WBPerformanceConfiguration

## SYNOPSIS
Retrieves the current volume backup performance settings.

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
PS C:\> Get-WBPerformanceConfiguration -OverallPerformanceSetting AlwaysIncremental
```

This example retrieves the global settings for all volumes with the AlwaysIncremental setting.

### Example 2: Retrieve settings for a volume
```
PS C:\> $Backup = Get-WBBackupSet
PS C:\> Get-WBPerformanceConfiguration -Volume $Backup.Volume[1] AlwaysFull
```

This example retrieves the settings for a specific volume with the AlwaysFull setting.

## PARAMETERS

### -OverallPerformanceSetting
If specified, indicates that the returned data is to be for the global setting.

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
Specifies the **WBVolume** object for which the current performance settings are retrieved.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### SwitchParameter, WBVolume
Indicates either global settings or volume settings.

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-WBPerformanceConfiguration](./Set-WBPerformanceConfiguration.md)

