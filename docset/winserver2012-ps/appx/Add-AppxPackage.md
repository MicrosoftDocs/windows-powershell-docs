---
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
Module Name: Appx
online version: https://docs.microsoft.com/powershell/module/appx/add-appxpackage?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-AppxPackage

## SYNOPSIS
Adds a signed app package to a user account.

## SYNTAX

### AddSet (Default)
```
Add-AppxPackage [-Path] <String> [-DependencyPath <String[]>] [-ForceApplicationShutdown] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### RegisterSet
```
Add-AppxPackage [-Path] <String> [-DependencyPath <String[]>] [-Register] [-DisableDevelopmentMode]
 [-ForceApplicationShutdown] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateSet
```
Add-AppxPackage [-Path] <String> [-DependencyPath <String[]>] [-ForceApplicationShutdown] [-Update] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AppxPackage** cmdlet adds a signed app package (.appx) to a user account.
An app package has an .appx file name extension.
Use the *DependencyPath* parameter to add all other packages that are required for the installation of the app package.

You can use the *Register* parameter to install from a folder of unpackaged files during development of Windows® Store apps.

To update an already installed package, the new package must have the same package family name.

## EXAMPLES

### Example 1: Add an app package
```
PS C:\>Add-AppxPackage -Path "C:\Users\user1\Desktop\MyApp.appx" -DependencyPath "C:\Users\user1\Desktop\winjs.appx"
```

This command adds an app package and the signing certificate that the package contains.

### Example 2: Add a disabled app package in development mode
```
PS C:\>$ManifestPath = (Get-AppxPackage -Name "*WindowsCalculator*").InstallLocation + "\Appxmanifest.xml"
PS C:\> Add-AppxPackage -Path $ManifestPath -Register -DisableDevelopmentMode
```

This command gets the full path of the package manifest file of an installed Windows Store app, and then registers that package.
You can use *DisableDevelopmentMode* to register an application that is staged by the **StagePackageAsync** API, has been disabled, or has become corrupted during testing.

## PARAMETERS

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

### -DependencyPath
Specifies an array of file paths of dependency packages that  are required for the installation of the app package.
The app package has an .appx or .appxbundle file name extension.
You can specify the paths to more than one dependency package.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableDevelopmentMode
Indicates that this cmdlet registers an existing app package installation that has been disabled, did not register, or has become corrupted.
Use the current parameter to specify that the manifest is from an existing installation, and not from a collection of files in development mode.
You can also use this parameter to register an application that the Package Manager APIhttps://go.microsoft.com/fwlink/?LinkId=245447 has staged.
Use the *Register* parameter to specify the location of the app package manifest .xml file from the installation location.

```yaml
Type: SwitchParameter
Parameter Sets: RegisterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceApplicationShutdown
Forces all active processes that are associated with the package or its dependencies to shut down.

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

### -Path
Specifies the file path of the app package.
An app package has an .appx or .appxbundle file name extension.

```yaml
Type: String
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Register
Indicates that this cmdlet registers an application in development mode.
You can use development mode to install applications from a folder of unpackaged files.
You can use the current parameter to test your Windows® Store apps before you deploy them as app packages.
To register an existing app package installation, you must specify the *DisableDevelopmentMode* parameter and the *Register* parameter.
In order to specify dependency packages, specify the *DependencyPath* parameter and the *DisableDevelopmentMode* parameter.

```yaml
Type: SwitchParameter
Parameter Sets: RegisterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Update
Indicates that the package being added is a dependency package update.
A dependency package is removed from the user account when the parent app is removed.
If you do not use this parameter, the package being added is a primary package and is not removed from the user account if the parent app is removed.
To update an already installed package, the new package must have the same package family name.

```yaml
Type: SwitchParameter
Parameter Sets: UpdateSet
Aliases: 

Required: True
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### System.IO.FileInfo

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[PackageManager class](https://go.microsoft.com/fwlink/?LinkId=245447)

[Sideload Apps with DISM](https://go.microsoft.com/fwlink/?LinkID=231020)

