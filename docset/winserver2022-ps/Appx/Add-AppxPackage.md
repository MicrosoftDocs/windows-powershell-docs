---
description: Adds a signed app package to a user account.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-help.xml
Module Name: Appx
ms.date: 05/15/2023
online version: https://learn.microsoft.com/powershell/module/appx/add-appxpackage?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-AppxPackage
---

# Add-AppxPackage

## SYNOPSIS
Adds a signed app package to a user account.

## SYNTAX

### AddSet (Default)

```
Add-AppxPackage [-Path] <String> [-DependencyPath <String[]>] [-RequiredContentGroupOnly]
 [-ForceApplicationShutdown] [-ForceTargetApplicationShutdown] [-ForceUpdateFromAnyVersion]
 [-RetainFilesOnFailure] [-InstallAllResources] [-Volume <AppxVolume>]
 [-ExternalPackages <String[]>] [-OptionalPackages <String[]>] [-RelatedPackages <String[]>]
 [-ExternalLocation <String>] [-DeferRegistrationWhenPackagesAreInUse]
 [-StubPackageOption <StubPackageOption>] [-AllowUnsigned] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AddByAppInstallerSet

```
Add-AppxPackage [-Path] <String> [-RequiredContentGroupOnly] [-AppInstallerFile]
 [-ForceTargetApplicationShutdown] [-InstallAllResources] [-LimitToExistingPackages]
 [-Volume <AppxVolume>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RegisterSet

```
Add-AppxPackage [-Path] <String> [-DependencyPath <String[]>] [-Register] [-DisableDevelopmentMode]
 [-ForceApplicationShutdown] [-ForceTargetApplicationShutdown] [-ForceUpdateFromAnyVersion]
 [-InstallAllResources] [-ExternalLocation <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateSet

```
Add-AppxPackage [-Path] <String> [-DependencyPath <String[]>] [-RequiredContentGroupOnly]
 [-ForceApplicationShutdown] [-ForceTargetApplicationShutdown] [-ForceUpdateFromAnyVersion]
 [-RetainFilesOnFailure] [-InstallAllResources] [-Update] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### StageSet

```
Add-AppxPackage [-Path] <String> [-DependencyPath <String[]>] [-RequiredContentGroupOnly] [-Stage]
 [-ForceUpdateFromAnyVersion] [-Volume <AppxVolume>] [-ExternalPackages <String[]>]
 [-OptionalPackages <String[]>] [-RelatedPackages <String[]>] [-ExternalLocation <String>]
 [-StubPackageOption <StubPackageOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RegisterByPackageFullNameSet

```
Add-AppxPackage [-Register] -MainPackage <String> [-DependencyPackages <String[]>]
 [-ForceApplicationShutdown] [-ForceTargetApplicationShutdown] [-ForceUpdateFromAnyVersion]
 [-InstallAllResources] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RegisterByPackageFamilyNameSet

```
Add-AppxPackage [-RegisterByFamilyName] -MainPackage <String> [-DependencyPackages <String[]>]
 [-ForceApplicationShutdown] [-ForceTargetApplicationShutdown] [-InstallAllResources]
 [-OptionalPackages <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Add-AppxPackage` cmdlet adds a signed app package to a user account. An app package has an
`.msix` or `.appx` filename extension. Use the **DependencyPath** parameter to add all other
packages required for the installation of the app package.

You can use the **Register** parameter to install from a folder of unpackaged files during
development of Windows Store apps.

To update an already installed package, the new package must have the same package family name.

## EXAMPLES

### Example 1: Add an app package

```powershell
Add-AppxPackage -Path '.\MyApp.msix' -DependencyPath '.\winjs.msix'
```

This command adds an app package that the package contains.

### Example 2: Update an app, but defer registration until the app has closed

```powershell
$params = @{
    Path = '.\MyApp.msix' 
    DependencyPath = '.\winjs.msix'
    DeferRegistrationWhenPackagesAreInUse = $true
}
Add-AppxPackage @params
```

This command will register an update to an existing app, but won't do so until the next launch of
the app.

### Example 3: Add a disabled app package in development mode

```powershell
$InstallLocation = Get-AppxPackage -Name '*WindowsCalculator*' |
    Select-Object -ExpandProperty InstallLocation
$ManifestPath = $InstallLocation + '\Appxmanifest.xml'
Add-AppxPackage -Path $ManifestPath -Register -DisableDevelopmentMode
```

This command gets the full path of the package manifest file of an installed Windows Store app, and
then registers that package. You can use **DisableDevelopmentMode** to register an application
that's staged by the **StagePackageAsync** API, has been disabled, or has become corrupted during
testing.

### Example 4: Add an app along with its optional packages

```powershell
Add-AppxPackage -Path '.\MyApp.msixbundle' -ExternalPackages @(
    '.\optionalpackage1.msix'
    '.\optionalpackage2.msixbundle'
)

Add-AppxPackage -Path '.\MyApp.msixbundle' -OptionalPackages '29270sandstorm.OptionalPackage1_gah1vdar1nn7a'
```

This command adds an app package along with its optional packages. It's an atomic operation, which
means that if the app or its optional packages fail to install, the deployment operation will be
aborted

### Example 5: Install only the required section of a streaming app

```powershell
Add-AppxPackage -Path '.\MyApp.msixbundle' -RequiredContentGroupOnly
```

This command adds an app package but only installs the required section of a streaming app. Calling
this command again without the **RequiredContentGroupOnly** parameter proceeds to install the rest
of the application in the order defined by the `AppxContentGroupMap.xml`

### Example 6: Install an app using the App Installer file

```powershell
Add-AppxPackage -AppInstallerFile "C:\Users\user1\Desktop\MyApp.appinstaller"
```

This command adds an app package as outlined in the App Installer file with all update settings
specified within the App Installer file, if any.

## PARAMETERS

### -AllowUnsigned

Allows adding an unsigned package.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AddSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AppInstallerFile

Runs an appinstaller file and allows the user to install all the defined packages with a single
click. For more information, see
[Create an App Installer file manually](/windows/msix/app-installer/how-to-create-appinstaller-file).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AddByAppInstallerSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeferRegistrationWhenPackagesAreInUse

Specifies that the app won't register for a user if currently in use. The app will update on the
next launch.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AddSet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DependencyPackages

Specifies the dependency package full name or dependency package bundle full name to be registered.

```yaml
Type: System.String[]
Parameter Sets: RegisterByPackageFullNameSet, RegisterByPackageFamilyNameSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DependencyPath

Specifies an array of file paths of dependency packages that are required for the installation of
the app package. The app package has an `.msix`, `.appx`, `.msixbundle`, or `.appxbundle` filename
extension. You can specify the paths to more than one dependency package. If a package is already
installed for a user, you can skip adding it to the DependencyPath.

```yaml
Type: System.String[]
Parameter Sets: AddSet, RegisterSet, UpdateSet, StageSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableDevelopmentMode

Indicates that this cmdlet registers an existing app package installation that has been disabled,
didn't register, or has become corrupted. Use the current parameter to specify that the manifest is
from an existing installation, and not from a collection of files in development mode. You can also
use this parameter to register an application that the
[Package Manager API](https://go.microsoft.com/fwlink/?LinkId=245447) has staged. Use the
**Register** parameter to specify the location of the app package manifest `.xml` file from the
installation location.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RegisterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExternalLocation

URI path of an external disk location outside of the MSIX package where the package manifest can
reference application content.

```yaml
Type: System.String
Parameter Sets: AddSet, RegisterSet, StageSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExternalPackages

Specifies an array of optional packages that must be installed along with the app package. It's an
atomic operation, which means that if the app or its optional packages fail to install, the
deployment operation will be aborted.

```yaml
Type: System.String[]
Parameter Sets: AddSet, StageSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceApplicationShutdown

Indicates that this cmdlet forces all active processes associated with the package or its
dependencies to shut down. If you specify this parameter, don't specify the
**ForceTargetApplicationShutdown** parameter.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AddSet, RegisterSet, UpdateSet, RegisterByPackageFullNameSet, RegisterByPackageFamilyNameSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceTargetApplicationShutdown

Indicates that this cmdlet forces all active processes associated with the package to shut down. If
you specify this parameter, don't specify the **ForceApplicationShutdown** parameter.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AddSet, AddByAppInstallerSet, RegisterSet, UpdateSet, RegisterByPackageFullNameSet, RegisterByPackageFamilyNameSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceUpdateFromAnyVersion

This parameter is used to force a specific version of a package to be staged or registered,
regardless of whether a higher version is already staged or registered.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AddSet, RegisterSet, UpdateSet, StageSet, RegisterByPackageFullNameSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstallAllResources

Indicates that this cmdlet forces the deployment of all resource packages specified from a bundle
argument. This overrides the resource applicability check of the deployment engine and forces
staging of all resource packages, registration of all resource packages, or staging and registration
of all resource packages. This parameter can only be used when specifying a resource bundle or
resource bundle manifest.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AddSet, AddByAppInstallerSet, RegisterSet, UpdateSet, RegisterByPackageFullNameSet, RegisterByPackageFamilyNameSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LimitToExistingPackages

This parameter is used to prevent missing referenced packages to be downloaded.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AddByAppInstallerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MainPackage

Specifies the main package full name or bundle full name to register.

```yaml
Type: System.String
Parameter Sets: RegisterByPackageFullNameSet, RegisterByPackageFamilyNameSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -OptionalPackages

Specifies the PackageFamilyName of the optional packages that are in a related set that need to be
installed along with the app. Unlike the external packages flag, you don't need to pass in a path
to the optional packages. It's an atomic operation, which means that if the app or its optional
packages fail to install, the deployment operation will be aborted.

```yaml
Type: System.String[]
Parameter Sets: AddSet, StageSet, RegisterByPackageFamilyNameSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Specifies the path to the app package file. An app package has an `.msix`, `.appx`, `.msixbundle`,
or `.appxbundle` filename extension.

```yaml
Type: System.String
Parameter Sets: AddSet, AddByAppInstallerSet, RegisterSet, UpdateSet, StageSet
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Register

Indicates that this cmdlet registers an application in development mode. You can use development
mode to install applications from a folder of unpackaged files. You can use the current parameter
to test your Windows Store apps before you deploy them as app packages. To register an existing app
package installation, you must specify the **DisableDevelopmentMode** parameter and the
**Register** parameter. To specify dependency packages, use the **DependencyPath** parameter and
the **DisableDevelopmentMode** parameter.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RegisterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RegisterByPackageFullNameSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RegisterByFamilyName

Specifies the parameter -MainPackage that defines the family name or full name to be registered.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RegisterByPackageFamilyNameSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RelatedPackages

This is an optional element that's used to specify the other optional packages that are specified
in the main app package. These packages won't be installed as part of the deployment operation.

```yaml
Type: System.String[]
Parameter Sets: AddSet, StageSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequiredContentGroupOnly

Specifies that only the required content group that's specified in the `AppxContentGroupMap.xml`
must be installed. At this point the app can be launched. Calling `Add-AppxPackage` and specifying
the path to the app triggers the rest of the app to be installed in the order defined in the
`AppxContentGroupMap.xml`.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AddSet, AddByAppInstallerSet, UpdateSet, StageSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetainFilesOnFailure

In case of a failed deployment, if this switch is set to `$true`, files that have been created on
the target machine during the installation process aren't removed.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AddSet, UpdateSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stage

Stages a package to the system without registering it.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: StageSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StubPackageOption

Defines the stub behavior for an app package that's being added or staged. The acceptable values
for this parameter are:

- `Default`: Uses the default behavior
- `InstallFull`: Installs as a full app
- `InstallStub`: Installs as a stub app
- `UsePreference`: Uses the current
  [PackageStubPreference](/uwp/api/windows.management.deployment.packagestubpreference) for the
  package

```yaml
Type: StubPackageOption
Parameter Sets: AddSet, StageSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Update

Specifies that the package being added is a dependency package update. A dependency package is
removed from the user account when the parent app is removed. If you don't use this parameter, the
package being added is a primary package and isn't removed from the user account if the parent app
is removed. To update an already installed package, the new package must have the same package
family name.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UpdateSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Volume

Specifies the **AppxVolume** object to stage the package in. The volume also specifies the default
location for user **AppData**.

```yaml
Type: AppxVolume
Parameter Sets: AddSet, AddByAppInstallerSet, StageSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### System.IO.FileInfo

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Package Manager API](https://go.microsoft.com/fwlink/?LinkId=245447)

[How to Add and Remove Apps](https://go.microsoft.com/fwlink/?LinkID=231020)

[Get-AppxPackage](./Get-AppxPackage.md)

[Get-AppxPackageManifest](./Get-AppxPackageManifest.md)

[Move-AppxPackage](./Move-AppxPackage.md)

[Remove-AppxPackage](./Remove-AppxPackage.md)
