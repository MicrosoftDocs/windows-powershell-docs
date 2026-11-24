---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
Module Name: AppvClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/appvclient/publish-appvclientpackage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-AppvClientPackage
---

# Publish-AppvClientPackage

## SYNOPSIS
Publishes the App-V package.

## SYNTAX

### ByGuid (Default)
```
Publish-AppvClientPackage [-Global] [-UserSID <String>] [[-DynamicUserConfigurationPath] <String>]
 [-DynamicUserConfigurationType <DynamicUserConfiguration>] [-PackageId] <Guid> [-VersionId] <Guid>
 [<CommonParameters>]
```

### ByPackage
```
Publish-AppvClientPackage [-Global] [-UserSID <String>] [[-DynamicUserConfigurationPath] <String>]
 [-DynamicUserConfigurationType <DynamicUserConfiguration>] [-Package] <AppvClientPackage> [<CommonParameters>]
```

### ByName
```
Publish-AppvClientPackage [-Global] [-UserSID <String>] [[-DynamicUserConfigurationPath] <String>]
 [-DynamicUserConfigurationType <DynamicUserConfiguration>] [-Name] <String> [[-Version] <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Publish-AppvClientPackage** cmdlet publishes the appropriate extension points of a set of Microsoft Application Virtualization (App-V) packages.
Examples of common extension points include shortcuts and FTAs.
You can publish the package to the current user or to all users that log into the targeted computer.
You can also provide a Dynamic User Configuration file for the package.

## EXAMPLES

### Example 1: Publish a version of a package to all users
```
PS C:\> Publish-AppvClientPackage -Name "MyApp" -Version 1 -Global -DynamicUserConfiguration "C:\content\policies\MyApp.policy"
```

This command publishes version 1 of the package named MyApp to all users on the computer and applies the Dynamic User Configuration policy file.

### Example 2: Publish a version of a package to a user
```
PS C:\> Publish-AppvClientPackage -Name "MyApp" -Version 1 -UserPolicy "C:\content\policies\MyAppConfiguration.xml"
```

This command publishes version 1 of the package named "MyApp" to the user and applies the Dynamic User Configuration policy file.

### Example 3: Publish the latest version of a package to all users
```
PS C:\> Publish-AppvClientPackage -Name "MyApp" -Global
```

This command publishes the package named MyApp to all users on the computer.

## PARAMETERS

### -DynamicUserConfigurationPath
Specifies the path of a Dynamic User configuration file for the specified App-V package to be added.
The cmdlet uses the Dynamic User Configuration file to override the default behavior provided in the user section of the package manifest or the Dynamic Deployment Configuration.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DynamicUserConfigurationType
Specifies what should be done without a defined dynamic user configuration file.
The acceptable values for this parameter are:

- UseDeploymentConfiguration.
The package uses the user configuration part of deployment configuration.
- UseNoConfiguration.
Clear any previous configuration and use settings from the manifest.
- UseExistingConfiguration.
Make no changes to the configuration and use the last published configuration.

If you do not specify this parameter, this cmdlet uses UseExistingConfiguration if the package is already published or UseDeploymentConfiguration if it is not.

Use this parameter only during user publishing.
It is not valid for global publish.

```yaml
Type: DynamicUserConfiguration
Parameter Sets: (All)
Aliases:
Accepted values: UseDeploymentConfiguration, UseNoConfiguration, UseExistingConfiguration

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Global
Indicates that the provided package is published to all users that log into the targeted computer.
Otherwise, the packages are only published to the currently running user.

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

### -Name
Specifies the name of the package given when it was sequenced.
This value is obtained from the package manifest.

```yaml
Type: String
Parameter Sets: ByName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Package
Specifies an App-V package.

```yaml
Type: AppvClientPackage
Parameter Sets: ByPackage
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PackageId
Specifies a GUID that identifies the package.
The information can be found in the package manifest or by opening the package in the App-V sequencer.
The package ID is shared by all versions of a package.

```yaml
Type: Guid
Parameter Sets: ByGuid
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserSID
Specifies the SID of the intended user, in the form of S-1-2-34-56789012-3456789012-345678901-2345.
This parameter requires elevated rights to run.

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

### -Version
Specifies the version of an App-V package in a lineage.
If you do not specify this parameter, the cmdlet operates on the latest of the package on the computer running the App-V client.

```yaml
Type: String
Parameter Sets: ByName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VersionId
Specifies a GUID that differentiates a package version from other versions.
If you do not specify this parameter, the cmdlet operates on the latest version of the package.

```yaml
Type: Guid
Parameter Sets: ByGuid
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.AppvAgent.AppvClientPackage

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AppvClientPackage](./Add-AppvClientPackage.md)

[Get-AppvClientPackage](./Get-AppvClientPackage.md)

[Mount-AppvClientPackage](./Mount-AppvClientPackage.md)

[Remove-AppvClientPackage](./Remove-AppvClientPackage.md)

[Repair-AppvClientPackage](./Repair-AppvClientPackage.md)

[Set-AppvClientPackage](./Set-AppvClientPackage.md)

[Stop-AppvClientPackage](./Stop-AppvClientPackage.md)

[Unpublish-AppvClientPackage](./Unpublish-AppvClientPackage.md)

