---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
Module Name: UEV
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/uev/clear-uevconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-UevConfiguration
---

# Clear-UevConfiguration

## SYNOPSIS
Clears UE-V configuration settings.

## SYNTAX

### ParameterSetUser (Default)
```
Clear-UevConfiguration [-CurrentComputerUser] [-MaxPackageSizeInBytes] [-SettingsStoragePath]
 [-SyncProviderPingEnabled] [-SyncTimeoutInMilliseconds] [-SyncMethod] [-SyncEnabled] [-SyncOverMeteredNetwork]
 [-SyncOverMeteredNetworkWhenRoaming] [-SettingsImportNotifyEnabled] [-SettingsImportNotifyDelayInSeconds]
 [-DontSyncWindows8AppSettings] [-WaitForSyncTimeoutInMilliseconds] [-WaitForSyncOnApplicationStart]
 [-WaitForSyncOnLogon] [-SyncUnlistedWindows8Apps] [-VdiCollectionName] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ParameterSetComputer
```
Clear-UevConfiguration [-Computer] [-MaxPackageSizeInBytes] [-SettingsStoragePath]
 [-SettingsTemplateCatalogPath] [-SyncProviderPingEnabled] [-SyncTimeoutInMilliseconds] [-SyncMethod]
 [-SyncEnabled] [-SyncOverMeteredNetwork] [-SyncOverMeteredNetworkWhenRoaming] [-SettingsImportNotifyEnabled]
 [-SettingsImportNotifyDelayInSeconds] [-ContactITUrl] [-ContactITDescription] [-TrayIconEnabled]
 [-FirstUseNotificationEnabled] [-DontSyncWindows8AppSettings] [-WaitForSyncTimeoutInMilliseconds]
 [-WaitForSyncOnApplicationStart] [-WaitForSyncOnLogon] [-SyncUnlistedWindows8Apps] [-VdiCollectionName]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Clear-UevConfiguration** cmdlet clears Microsoft User Experience Virtualization (UE-V) configuration settings.
If you specify the *CurrentComputerUser* parameter, the cmdlet clears the settings that you specify for the current user only.
If you specify the *Computer* parameter, the cmdlet clears the settings that you specify for all users on the computer.
You must have administrative credentials to use this cmdlet to clear settings for all users on the computer.
If you do not specify the *CurrentComputerUser* or *Computer* parameter, the cmdlet clears the settings that you specify for the current user only.

## EXAMPLES

### Example 1: Clear the setting for maximum package size for all users
```
PS C:\> Clear-UevConfiguration -Computer -MaxPackageSizeInBytes
```

This command clears the setting for maximum package size for all users on the computer.

### Example 2: Clear the setting for maximum package size for the current user
```
PS C:\> Clear-UevConfiguration -CurrentComputerUser -MaxPackageSizeInBytes
```

This command clears the setting for maximum package size for the current user.

### Example 3: Clear the setting for maximum package size by default for the current user
```
PS C:\> Clear-UevConfiguration -MaxPackageSizeInBytes
```

This command clears the setting for maximum package size by default for the current user.

### Example 4: Clear multiple settings for the current user
```
PS C:\> Clear-UevConfiguration -MaxPackageSizeInBytes -SyncTimeoutInMilliseconds
```

This command clears the settings for maximum package size and synchronization timeout for the current user.

## PARAMETERS

### -Computer
Indicates that the cmdlet clears the settings for all users on the computer.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetComputer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContactITDescription
Indicates that the cmdlet clears the setting for the description of the Contact IT link.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetComputer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContactITUrl
Indicates that the cmdlet clears the setting for the URL of the Contact IT link.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetComputer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CurrentComputerUser
Indicates that the cmdlet clears the settings that you specify for the current user only.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetUser
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DontSyncWindows8AppSettings
Indicates that the cmdlet clears the setting for not synchronizing settings for Windows® 8 apps.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FirstUseNotificationEnabled
Indicates that the cmdlet clears the setting for the notification of first-use.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetComputer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxPackageSizeInBytes
Indicates that the cmdlet clears the setting for the maximum package size.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SettingsImportNotifyDelayInSeconds
Indicates that the cmdlet clears the setting for the delay before UE-V notifies the user about the settings import.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SettingsImportNotifyEnabled
Indicates that the cmdlet clears the setting for the notification of settings import.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SettingsStoragePath
Indicates that the cmdlet clears the setting for the path of the location where UE-V stores the user settings.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SettingsTemplateCatalogPath
Indicates that the cmdlet clears the setting for the path of the location where UE-V stores the settings template catalog.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetComputer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SyncEnabled
Indicates that the cmdlet clears the setting that enables the synchronization of settings.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SyncMethod
Indicates that the cmdlet clears the setting for the method of the synchronization of settings.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SyncOverMeteredNetwork
Indicates that the cmdlet clears the setting for synchronization over metered connections.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SyncOverMeteredNetworkWhenRoaming
Indicates that the cmdlet clears the setting for synchronization over a metered connection that is roaming.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SyncProviderPingEnabled
Indicates that the cmdlet clears the setting that enables the sync provider to ping for network access before doing a sync.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SyncTimeoutInMilliseconds
Indicates that the cmdlet clears the setting for the timeout before UE-V synchronizes settings from the settings repository.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SyncUnlistedWindows8Apps
Indicates that the cmdlet clears the setting for the synchronization of unlisted Windows 8 apps.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrayIconEnabled
Indicates that the cmdlet clears the setting for the icon in the notification area.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetComputer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VdiCollectionName
Indicates that the cmdlet performs synchronization in a pooled VDI-type environment when computers are not persistent.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WaitForSyncOnApplicationStart
Indicates that the cmdlet clears the setting for waiting for synchronization to finish before the user can start an application.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WaitForSyncOnLogon
Indicates that the cmdlet clears the setting for waiting for synchronization to finish before the user can log on.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WaitForSyncTimeoutInMilliseconds
For internal use only.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-UevConfiguration](./Get-UevConfiguration.md)

[Set-UevConfiguration](./Set-UevConfiguration.md)

[Import-UevConfiguration](./Import-UevConfiguration.md)

[Export-UevConfiguration](./Export-UevConfiguration.md)

