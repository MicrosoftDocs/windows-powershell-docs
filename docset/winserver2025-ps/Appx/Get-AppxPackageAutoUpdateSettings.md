---
description: Provides guidance on how to view the auto-update and repair settings of a Windows App.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-help.xml
Module Name: Appx
ms.date: 05/15/2023
online version: https://learn.microsoft.com/powershell/module/appx/Get-AppxPackageAutoUpdateSettings?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-AppxPackageAutoUpdateSettings

## SYNOPSIS

Provides visibility to the settings configured for a particular Windows App.

## SYNTAX

```
Get-AppxPackageAutoUpdateSettings [[-PackageFullName] <String>] [-ShowUpdateAvailability]
 [-AllUsers] [<CommonParameters>]
```

## DESCRIPTION

The `Get-AppxPackageAutoUpdateSettings` PowerShell cmdlet returns the settings configured for a
specific or all installed Windows Apps in relation to Auto Update and Repair.

## EXAMPLES

### Example 1: Get all App Package Auto Update settings

```powershell
Get-AppxPackageAutoUpdateSettings
```

This will return the Auto Update and Repair settings for all configured and installed Windows Apps
on the device, and registered to the user.

### Example 2: Get App Package Auto Update settings for all users

```powershell
Get-AppxPackageAutoUpdateSettings -AllUsers
```

This will return the Auto Update and Repair settings for all configured and installed Windows Apps
that have been registered for all users.

### Example 3: Get a single App Package Auto Update setting

```powershell
Get-AppxPackageAutoUpdateSettings -PackageFullName publisher.package1_1.0.0.0_neutral__8wekyb3d8bbwe
```

This will return the Auto Update and Repair settings for a specific Windows App that has been
installed and registered to the signed-in user.

### Example 4: Get App Package Auto Update settings for all installed Windows Apps

```powershell
Get-AppxPackageAutoUpdateSettings -ShowUpdateAvailability
```

Displays available update information for all installed Windows Apps.

## PARAMETERS

### -PackageFullName

Specifies the Package Full Name of the app that's being queried.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -ShowUpdateAvailability

Specifies to display available update information for a specific Windows App.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -AllUsers

Specifies to display Windows App Auto Update and Repair settings for all that are installed for all
users.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```


### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Package Manager API](http://go.microsoft.com/fwlink/?LinkId=245447)

[How to Add and Remove Apps](http://go.microsoft.com/fwlink/?LinkID=231020)

[Get-AppxPackage](./Get-AppxPackage.md)

[Get-AppxPackageManifest](./Get-AppxPackageManifest.md)

[Move-AppxPackage](./Move-AppxPackage.md)

[Remove-AppxPackage](./Remove-AppxPackage.md)
