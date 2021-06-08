---
description: Provides guidance on how to configure the auto-update and repair settings of a Windows App.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-help.xml
Module Name: Appx
ms.date: 06/07/2021
online version: https://docs.microsoft.com/powershell/module/appx/reset-appxpackage?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AppxPackageAutoUpdateSettings
---

# Set-AppxPackageAutoUpdateSettings

## SYNOPSIS
Available in the Windows Insider Preview Builds of windows 10, is the `Set-AppxPackageAutoUpdateSettings` PowerShell cmdlet. The `Set-AppxPackageAutoUpdateSettings` PowerShell cmdlet provides access to configure a specific Windows App's Auto Update and Repair settings. Including pausing update checks.

## SYNTAX

### SetAutoUpdateOptionsSet (Default)
```PowerShell
Set-AppxPackageAutoUpdateSettings 
                -PackageFamilyName <string>
                -AppInstallerURI <string>
                [-CheckOnLaunch]
                [-Confirm]
                [-DependencyPackages] <string>
                [-DisableAutoRepair]
                [-EnableAutomaticBackgroundTask]
                [-ForceUpdateFromAnyVersion]
                [-HoursBetweenUpdateChecks] <int>
                [-OptionalPackages] <string>
                [-RepairUris] <string>
                [-ShowPrompt]
                [-UpdateBlocksActivation]
                [-UpdateUris] <string>
                [-UseSystemPolicySource]
                [-Version] <string>
                [-WhatIf] 
                [-Confirm] 
                [<CommonParameters>]
```

### PauseAutoUpdateOptionsSet
```PowerShell
Set-AppxPackageAutoUpdateSettings 
                -PackageFamilyName <string>
                -PauseUpdates
                -HoursToPause <int>
                [-UseSystemPolicySource]
                [-WhatIf] 
                [-Confirm] 
                [<CommonParameters>]
```

## DESCRIPTION
The **Set-AppxPackageAutoUpdateSettings** cmdlet provides access to configure a specific Windows App's Auto Update and Repair seetings. 

## EXAMPLES

### Example 1: Update the Auto-Update settings for an App
```
PS C:\> Set-AppxPackageAutoUpdateSettings -AppInstallerUri https://website.com/PackageName.appinstaller -PackageFamilyName PackageName_8h66172c634n0 -CheckOnLaunch -ForceUpdateFromAnyVersion -HoursBetweenUpdateChecks 2 -ShowPrompt -UpdateUris file://ComputerName/Share/PackageName_x64.appinstaller
```

This cmdlet will update the Auto-Update settings of the *PackageName_8h66172c634n0* Windows App to target an AppInstaller file on a network accessible file share every two hours, displaying a prompt to the user. Allowing for the Windows App to update to any version (higher or lower) despite the version of the installed Windows App.

### Example 2: Disable the Auto-Repair setting for an App
```
PS C:\> et-AppxPackageAutoUpdateSettings -AppInstallerUri https://website.com/PackageName.appinstaller -PackageFamilyName PackageName_8h66172c634n0 -DisableAutoRepairs
```

This cmdlet will disable the automatic repair of the Windows App.

### Example 3: Pause Updates on a specific Windows App
```
PS C:\> Set-AppxPackageAutoUpdateSettings -HoursToPause 4320 -PackageFamilyName PackageName_8h66172c634n0 -PauseUpdates
```

This cmdlet will pause the Windows App from checking for App updates for 4320 hours (180 Days).

### Example 3: Pause Updates on a specific Windows App
```
PS C:\> Set-AppxPackageAutoUpdateSettings -HoursToPause 0 -PackageFamilyName PackageName_8h66172c634n0 -PauseUpdates
```

This cmdlet will re-enable automatic updating of the Windows App.

## PARAMETERS

### -HoursToPause
Specifies the duration of time in hours, that the Windows App will not check for updates.

```yaml
Type: Int
Parameter Sets: SetAutoUpdateOptionsSet, PauseAutoUpdateOptionsSet
Aliases: None

Required: True
Position: N/A
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageFamilyName
Specifies the Package Family Name of the Windows App which is being modified.

```yaml
Type: String
Parameter Sets: SetAutoUpdateOptionsSet, PauseAutoUpdateOptionsSet
Aliases: None

Required: True
Position: 0
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -AppInstallerUri
Specifies the location of the AppInstaller file targetted by this Windows App.

```yaml
Type: String[]
Parameter Sets: SetAutoUpdateOptionsSet
Aliases: None

Required: True
Position: N/A
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CheckOnLaunch
Specifies that the Windows App will check for new updates when the App is launched.

```yaml
Type: Switch
Parameter Sets: SetAutoUpdateOptionsSet
Aliases: None

Required: False
Position: N/A
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DependencyPackages
Specifies any Dependency Packages being used by the Windows App.

```yaml
Type: String[]
Parameter Sets: SetAutoUpdateOptionsSet
Aliases: None

Required: False
Position: N/A
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableAutoRepairs
Turns off the automatic repair of a broken Windows App.

```yaml
Type: Switch
Parameter Sets: SetAutoUpdateOptionsSet
Aliases: None

Required: False
Position: N/A
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableAutomaticBackgroundTask
Specifies that the automation of updating and repairing will occur as a background task.

```yaml
Type: Switch
Parameter Sets: SetAutoUpdateOptionsSet
Aliases: None

Required: False
Position: N/A
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceUpdateFromAnyVersion
Specifies that the next update of the Windows App can be of a higher, or lower version.

```yaml
Type: Switch
Parameter Sets: SetAutoUpdateOptionsSet
Aliases: None

Required: False
Position: N/A
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HoursBetweenUpdateChecks
Specifies the time between update checks allowed for a specific Windows App.

```yaml
Type: Int
Parameter Sets: SetAutoUpdateOptionsSet
Aliases: None

Required: False
Position: N/A
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OptionalPackages
Specifies the Optional Packages being used by the Windows App.

```yaml
Type: String[]
Parameter Sets: SetAutoUpdateOptionsSet
Aliases: None

Required: False
Position: N/A
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RepairUris
Specifies the location which will be sourced from when repairing the Windows App.

```yaml
Type: String[]
Parameter Sets: SetAutoUpdateOptionsSet
Aliases: None

Required: False
Position: N/A
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShowPrompt
Specifies that if any action is occurring for the Windows App, a prompt will be displayed.

```yaml
Type: Switch
Parameter Sets: SetAutoUpdateOptionsSet
Aliases: None

Required: False
Position: N/A
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateBlocksActivation
Specifies that if an update is available for a Windows App, the App will prevent launching until the update has been installed.

```yaml
Type: Switch
Parameter Sets: SetAutoUpdateOptionsSet
Aliases: None

Required: False
Position: N/A
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateUris
Specifies the location which will be sourced from when updating the Windows App.

```yaml
Type: String[]
Parameter Sets: SetAutoUpdateOptionsSet
Aliases: None

Required: False
Position: N/A
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSystemPolicySource
Specifies that an override can be applied to the Developer set settings.

```yaml
Type: Switch
Parameter Sets: SetAutoUpdateOptionsSet, PauseAutoUpdateOptionsSet
Aliases: None

Required: False
Position: N/A
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Version
Specifies the version of the Update Settings being applied.

```yaml
Type: String
Parameter Sets: SetAutoUpdateOptionsSet, PauseAutoUpdateOptionsSet
Aliases: None

Required: False
Position: N/A
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### System.IO.FileInfo

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Package Manager API](http://go.microsoft.com/fwlink/?LinkId=245447)

[How to Add and Remove Apps](http://go.microsoft.com/fwlink/?LinkID=231020)

[Get-AppxPackage](./Get-AppxPackage.md)

[Get-AppxPackageManifest](./Get-AppxPackageManifest.md)

[Move-AppxPackage](./Move-AppxPackage.md)

[Remove-AppxPackage](./Remove-AppxPackage.md)
