---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Set-AppvClientPackage
---

# Set-AppvClientPackage

## SYNOPSIS
Configures an App-V Client Package.

## SYNTAX

### ByGuid (Default)
```
Set-AppvClientPackage [-Path <String>] [-DynamicDeploymentConfiguration <String>] [-UseNoConfiguration]
 [-PackageId] <Guid> [-VersionId] <Guid> [<CommonParameters>]
```

### ByPackage
```
Set-AppvClientPackage [-Path <String>] [-DynamicDeploymentConfiguration <String>] [-UseNoConfiguration]
 [-Package] <AppvClientPackage> [<CommonParameters>]
```

### ByName
```
Set-AppvClientPackage [-Path <String>] [-DynamicDeploymentConfiguration <String>] [-UseNoConfiguration]
 [-Name] <String> [[-Version] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AppvClientPackage** cmdlet modifies the configuration files of a Microsoft Application Virtualization (App-V) package.

## EXAMPLES

### Example 1: Set a deployment configuration for a package
```
PS C:\> Set-AppvClientPackage -Name "MyApp" -Version 1 -DynamicDeploymentConfiguration "C:\policies\MyApp.xml"
```

This command sets a new deployment configuration for a package.

## PARAMETERS

### -DynamicDeploymentConfiguration
Specifies the path to a Dynamic Deployment Configuration file for the App-V package to be added.
The cmdlet uses the Dynamic Deployment Configuration file to override the default behavior provided in the package manifest.

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

### -Name
Specifies the friendly name of the package given during Sequencing time.
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
Not Specified.

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
Specifies the GUID that uniquely identifies the package.
It can be found in the package manifest or by opening the package in the App-V Sequencer.
The package ID is shared by all versions of a specific package.

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

### -Path
Specifies the path specifies the location of the .APPV file containing the package to be added.
This parameter can point to a local directory, a network directory, or an HTTP or HTTPS URL.

```yaml
Type: String
Parameter Sets: (All)
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseNoConfiguration
Indicates that the cmdlet applies the default computer policy to the selected package.

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

### -Version
Specifies the version of an App-V package in a lineage.
If you do not specify this parameter, the cmdlet operates on all available versions of the package on the target computer.

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
Specifies a GUID that differentiates a package version from other versions, whether older, newer, or of a completely different lineage.
If you do not specify this parameter, the cmdlet operates on all versions of the package.

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

### Microsoft.AppvAgent.AppvClientPackage

## NOTES

## RELATED LINKS

[Add-AppvClientPackage](./add-appvclientpackage.md)

[Get-AppvClientPackage](./get-appvclientpackage.md)

[Mount-AppvClientPackage](./mount-appvclientpackage.md)

[Publish-AppvClientPackage](./publish-appvclientpackage.md)

[Publish-AppvClientPackage](./publish-appvclientpackage.md)

[Remove-AppvClientPackage](./remove-appvclientpackage.md)

[Repair-AppvClientPackage](./repair-appvclientpackage.md)

[Stop-AppvClientPackage](./stop-appvclientpackage.md)

[Unpublish-AppvClientPackage](./unpublish-appvclientpackage.md)
