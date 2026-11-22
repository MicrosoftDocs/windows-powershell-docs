---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
Module Name: UEV
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/uev/set-uevconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-UevConfiguration
---

# Set-UevConfiguration

## SYNOPSIS
Modifies UE-V configuration settings.

## SYNTAX

### ParameterSetUser (Default)
```
Set-UevConfiguration [-CurrentComputerUser] [-MaxPackageSizeInBytes <Int32>] [-SettingsStoragePath <String>]
 [-EnableSyncProviderPing] [-DisableSyncProviderPing] [-SyncTimeoutInMilliseconds <Int32>]
 [-SyncMethod <String>] [-EnableSync] [-DisableSync] [-EnableSyncOverMeteredNetwork]
 [-DisableSyncOverMeteredNetwork] [-EnableSyncOverMeteredNetworkWhenRoaming]
 [-DisableSyncOverMeteredNetworkWhenRoaming] [-EnableSettingsImportNotify] [-DisableSettingsImportNotify]
 [-SettingsImportNotifyDelayInSeconds <Int32>] [-EnableDontSyncWindows8AppSettings]
 [-DisableDontSyncWindows8AppSettings] [-WaitForSyncTimeoutInMilliseconds <Int32>]
 [-EnableWaitForSyncOnApplicationStart] [-DisableWaitForSyncOnApplicationStart] [-EnableWaitForSyncOnLogon]
 [-DisableWaitForSyncOnLogon] [-EnableSyncUnlistedWindows8Apps] [-DisableSyncUnlistedWindows8Apps]
 [-VdiCollectionName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ParameterSetComputer
```
Set-UevConfiguration [-Computer] [-MaxPackageSizeInBytes <Int32>] [-SettingsStoragePath <String>]
 [-SettingsTemplateCatalogPath <String>] [-EnableSyncProviderPing] [-DisableSyncProviderPing]
 [-SyncTimeoutInMilliseconds <Int32>] [-SyncMethod <String>] [-EnableSync] [-DisableSync]
 [-EnableSyncOverMeteredNetwork] [-DisableSyncOverMeteredNetwork] [-EnableSyncOverMeteredNetworkWhenRoaming]
 [-DisableSyncOverMeteredNetworkWhenRoaming] [-EnableSettingsImportNotify] [-DisableSettingsImportNotify]
 [-SettingsImportNotifyDelayInSeconds <Int32>] [-ContactITUrl <String>] [-ContactITDescription <String>]
 [-EnableTrayIcon] [-DisableTrayIcon] [-EnableFirstUseNotification] [-DisableFirstUseNotification]
 [-EnableDontSyncWindows8AppSettings] [-DisableDontSyncWindows8AppSettings]
 [-WaitForSyncTimeoutInMilliseconds <Int32>] [-EnableWaitForSyncOnApplicationStart]
 [-DisableWaitForSyncOnApplicationStart] [-EnableWaitForSyncOnLogon] [-DisableWaitForSyncOnLogon]
 [-EnableSyncUnlistedWindows8Apps] [-DisableSyncUnlistedWindows8Apps] [-VdiCollectionName <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-UevConfiguration** cmdlet modifies Microsoft User Experience Virtualization (UE-V) configuration settings.
If you specify the *CurrentComputerUser* parameter, the cmdlet changes the settings that you specify for the current user only.
If you specify the *Computer* parameter, the cmdlet clears the settings that you specify for all users on the computer.
You must have administrative credentials to use this cmdlet to modify settings for all users on the computer.
If you do not specify the *CurrentComputerUser* or *Computer* parameter, the cmdlet changes the settings that you specify for the current user only.

## EXAMPLES

### Example 1: Modify the synchronization timeout setting for all users
```
PS C:\> Set-UevConfiguration -Computer -SyncTimeoutInMilliseconds 3000
```

This command modifies the synchronization timeout setting to three seconds for all users on the computer.

### Example 2: Modify the synchronization timeout setting for the current user
```
PS C:\> Set-UevConfiguration -CurrentComputerUser -SyncTimeoutInMilliseconds 3000
```

This command modifies the synchronization timeout setting to three seconds for the current user on the computer.

### Example 3: Modify the synchronization timeout setting for the current user by default
```
PS C:\> Set-UevConfiguration -SyncTimeoutInMilliseconds 3000
```

This command modifies the synchronization timeout setting to three seconds by default for the current user on the computer.

### Example 4: Modify multiple settings for the current user
```
PS C:\> Set-UevConfiguration -CurrentComputerUser -SyncTimeoutInMilliseconds 5000 -MaxPackageSizeInBytes 700000
```

This command modifies the settings for the synchronization timeout and maximum package size for the current user on the computer.

## PARAMETERS

### -Computer
Indicates that the cmdlet changes the settings that you specify for all users on the computer.

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
Specifies a description for the Contact IT link.

```yaml
Type: String
Parameter Sets: ParameterSetComputer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContactITUrl
Specifies a URL for the Contact IT link.

```yaml
Type: String
Parameter Sets: ParameterSetComputer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CurrentComputerUser
Indicates that the cmdlet modifies the settings that you specify for the current user only.

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

### -DisableDontSyncWindows8AppSettings
Indicates that the cmdlet disables the setting for not synchronizing Windows® 8 app settings.
If you specify this parameter, UE-V synchronizes Windows 8 app settings.

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

### -DisableFirstUseNotification
Indicates that the cmdlet disables the notification of first-use.

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

### -DisableSettingsImportNotify
Indicates that the cmdlet disables the notification of settings import.
If you specify this parameter, UE-V does not notify the user about the settings import.

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

### -DisableSync
Indicates that the cmdlet disables the synchronization of settings.
If you specify this parameter, UE-V stops the synchronization of settings.

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

### -DisableSyncOverMeteredNetwork
Indicates that the cmdlet disables the synchronization of settings over metered connections.

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

### -DisableSyncOverMeteredNetworkWhenRoaming
Indicates that the cmdlet disables the synchronization of settings over metered connections outside of the home provider network, for example, when connected by using a roaming connection.

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

### -DisableSyncProviderPing
Indicates that the cmdlet disables the synchronization provider from pinging the network before it synchronizes.
If you specify this parameter, UE-V attempts to synchronize settings, even if the network is not available.

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

### -DisableSyncUnlistedWindows8Apps
Indicates that the cmdlet disables the synchronization of unlisted Windows 8 apps.

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

### -DisableTrayIcon
Indicates that the cmdlet disables the icon in the notification area.

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

### -DisableWaitForSyncOnApplicationStart
Indicates that the cmdlet disables UE-V from waiting for synchronization to finish before the user can start an application.

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

### -DisableWaitForSyncOnLogon
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

### -EnableDontSyncWindows8AppSettings
Indicates that the cmdlet enables the setting for not synchronizing Windows 8 app settings.
If you specify this parameter, UE-V does not synchronize Windows 8 app settings.

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

### -EnableFirstUseNotification
Indicates that the cmdlet enables first use notification.

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

### -EnableSettingsImportNotify
Indicates that the cmdlet enables the notification for settings import.
If the settings import takes longer than the amount of time that you specify for the *SettingsImportNotifyDelayInSecond* parameter, UE-V notifies the user.

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

### -EnableSync
Indicates that the cmdlet enables the synchronization of settings.
UE-V synchronizes the settings that are defined in the settings location templates that you have enabled.

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

### -EnableSyncOverMeteredNetwork
Indicates that the cmdlet enables the synchronization of settings over metered connections.

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

### -EnableSyncOverMeteredNetworkWhenRoaming
Indicates that the cmdlet enables the synchronization of settings over metered connections outside of the home provider network, for example, when connected by using a roaming connection.

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

### -EnableSyncProviderPing
Indicates that the cmdlet enables the synchronization provider to ping for network accessibility.
If you specify this parameter, UE-V attempts to synchronize settings only if the network is available.

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

### -EnableSyncUnlistedWindows8Apps
Indicates that the cmdlet enables the synchronization of unlisted Windows 8 apps.

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

### -EnableTrayIcon
Indicates that the cmdlet enables the icon in the notification area.

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

### -EnableWaitForSyncOnApplicationStart
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

### -EnableWaitForSyncOnLogon
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

### -MaxPackageSizeInBytes
Specifies the maximum package size, in bytes.
If the size of a package exceeds the value that you specify, UE-V logs a warning.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SettingsImportNotifyDelayInSeconds
Specifies the time, in seconds, before UE-V notifies the user about the settings import.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SettingsStoragePath
Specifies the path of the location where UE-V stores the user settings.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SettingsTemplateCatalogPath
Specifies the path of the location where UE-V stores the settings template catalog.

```yaml
Type: String
Parameter Sets: ParameterSetComputer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SyncMethod
Specifies the method for the synchronization of settings.
Valid values are:

- SyncProvider
- None

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SyncTimeoutInMilliseconds
Specifies the time, in milliseconds, before UE-V synchronizes settings from the settings repository.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VdiCollectionName
Specifies the name of the collection of computers that should share/sync settings.
Specify this parameter when you are performing synchronization in a pooled VDI-type environment when computers are not persistent.

```yaml
Type: String
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
Type: Int32
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

[Clear-UevConfiguration](./Clear-UevConfiguration.md)

[Import-UevConfiguration](./Import-UevConfiguration.md)

[Export-UevConfiguration](./Export-UevConfiguration.md)

