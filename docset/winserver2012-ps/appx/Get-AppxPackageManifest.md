---
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
Module Name: Appx
online version: https://learn.microsoft.com/powershell/module/appx/get-appxpackagemanifest?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-AppxPackageManifest

## SYNOPSIS
Gets the manifest of an app package.

## SYNTAX

```
Get-AppxPackageManifest [-Package] <AppxPackage> [[-User] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppxPackageManifest** cmdlet gets the manifest of an app package.
An app package has an .appx file name extension.
The manifest is an .xml document that contains information about the package, like the package ID.

## EXAMPLES

### Example 1: Get the manifest for an app package
```
PS C:\>Get-AppxPackageManifest -Package "package1_1.0.0.0_neutral__8wekyb3d8bbwe"
```

This command gets the manifest for an app package named package1_1.0.0.0_neutral__8wekyb3d8bbwe.

### Example 2: Get the application ID for an app package
```
PS C:\>(Get-AppxPackage -Name "*WinJS*" | Get-AppxPackageManifest).package.applications.application.id
```

This command gets the application ID for an app package that has the string WinJS in the name.

### Example 3: Get app capabilities
```
PS C:\>(Get-AppxPackage -Name "*ZuneMusic*" | Get-AppxPackageManifest).Package.Capabilities
```

This command gets the capabilities for an app package that has the string ZuneMusic in the name.

## PARAMETERS

### -Package
Specifies an **AppxPackage** object or the full name of a package.
To get the manifest of a package on the computer that is not installed for the current user, you must run this command by using administrator permissions.
Wildcards are permitted.

```yaml
Type: AppxPackage
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -User
Specifies a user.
This cmdlet gets the manifest of packages that are installed for the user that this parameter specifies.
To get the list of packages for a user profile other than the profile for the current user, you must run this command by using administrator permissions.
The user name can be in one of these formats: 

- domain\user_name
- user_name@fqn.domain.tld
- user_name
- SID-string

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Windows.Appx.PackageManager.Commands.AppxPackage[]
This cmdlet accepts an array of **AppxPackage** objects that contain information, including the full name of the app package.

## OUTPUTS

### System.XML.XMLDocument
This cmdlet returns a read-only .xml document that contains information about the app package, like the package ID.

## NOTES

## RELATED LINKS

[PackageManager class](https://go.microsoft.com/fwlink/?LinkId=245447)

[Sideload Apps with DISM](https://go.microsoft.com/fwlink/?LinkID=231020)

