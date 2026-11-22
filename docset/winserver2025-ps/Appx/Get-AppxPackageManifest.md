---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
Module Name: Appx
ms.date: 05/15/2023
online version: https://learn.microsoft.com/powershell/module/appx/get-appxpackagemanifest?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AppxPackageManifest
---

# Get-AppxPackageManifest

## SYNOPSIS
Gets the manifest of an app package.

## SYNTAX

```
Get-AppxPackageManifest [-Package] <String> [[-User] <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Get-AppxPackageManifest` cmdlet gets the manifest of an app package. An app package has an
`.msix` or `.appx` file name extension. The manifest is an `.xml` document that contains
information about the package, like the package ID.

## EXAMPLES

### Example 1: Get the manifest for an app package

```powershell
Get-AppxPackageManifest -Package "package1_1.0.0.0_neutral__8wekyb3d8bbwe"
```

This command gets the manifest for an app package named package1_1.0.0.0_neutral__8wekyb3d8bbwe.

### Example 2: Get the application ID for an app package

```powershell
(Get-AppxPackage -Name "*WinJS*" | Get-AppxPackageManifest).package.applications.application.id
```

This command gets the application ID for an app package that has the string WinJS in the name.

### Example 3

```powershell
(Get-AppxPackage -Name "*ZuneMusic*" | Get-AppxPackageManifest).Package.Capabilities
```

This command gets the capabilities for an app package that has the string ZuneMusic in the name.

## PARAMETERS

### -Package

Specifies an **AppxPackage** object or the full name of a package. To get the manifest of a package
on the computer that's not installed for the current user, you must run this command with
administrator permissions. Wildcards are permitted.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -User

Specifies a user. This cmdlet gets the manifest of packages that are installed for the user that
this parameter specifies. To get the list of packages for a user profile other than the profile for
the current user, you must run this command with administrator permissions. The user name can be
in one of these formats:

- `domain\user_name`
- `user_name@fqn.domain.tld`
- `user_name`
- `SID-string`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Windows.Appx.PackageManager.Commands.AppxPackage[]

This cmdlet accepts an array of **AppxPackage** objects that contain information, including the full
name of the app package.

## OUTPUTS

### System.XML.XMLDocument

This cmdlet returns a read-only `.xml` document that contains information about the app package,
like the package ID.

## NOTES

## RELATED LINKS

[Package Manager API](https://go.microsoft.com/fwlink/?LinkId=245447)

[How to Add and Remove Apps](https://go.microsoft.com/fwlink/?LinkID=231020)

[Get-AppxPackage](./Get-AppxPackage.md)

[Add-AppxPackage](./Add-AppxPackage.md)
