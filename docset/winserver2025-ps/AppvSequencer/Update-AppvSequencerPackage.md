---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.AppV.Modernizer.Cmdlets.dll-Help.xml
Module Name: AppvSequencer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/appvsequencer/update-appvsequencerpackage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-AppvSequencerPackage
---

# Update-AppvSequencerPackage

## SYNOPSIS
Upgrades virtual application packages.

## SYNTAX

```
Update-AppvSequencerPackage [-FullLoad] [-InputPackagePath] <String> [-Installer] <String[]>
 [-InstallerOptions <String[]>] [-Name] <String> [-Path] <String> [-TemplateFilePath <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Update-AppvSequencerPackage** cmdlet upgrades virtual application packages.
It takes as an input the original package, the upgrade installer, and an output path.
The cmdlet returns a package that is upgraded.

## EXAMPLES

### Example 1: Update an application
```
PS C:\> Update-AppvSequencerPackage -AppvPackageFilePath "C:\Packages\MyPackage.appv" -Installer "C:\PackageInstall\PackageUpgrade.exe" -OutputPath "C:\UpgradedPackages"
```

This command updates an application, changing the output path.

### Example 2: Update an application and require package to be fully loaded
```
PS C:\> Update-AppvSequencerPackage -AppvPackageFilePath "C:\Packages\MyPackage.appv" -Installer "C:\PackageInstall\PackageUpgrade.exe" -OutputPath "C:\UpgradedPackages" -FullLoad
```

This command updates an application, and sets the package to be fully loaded.

## PARAMETERS

### -FullLoad
Indicates that the cmdlet forces the package to be fully downloaded onto the computer before it can be launched.

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

### -InputPackagePath
Specifies the path of the existing Microsoft Application Virtualization (App-V) package to upgrade.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Installer
Specifies the installer used to upgrade the App-V package.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstallerOptions
Specifies an array of Installer Command-Line Options as parameter values, such as /quiet, /passive, or /norestart.

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

### -Name
Specifies the friendly name of the package given during Sequencing time.
This value is obtained from the package manifest.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path of the folder where the updated package is to be saved.

```yaml
Type: String
Parameter Sets: (All)
Aliases: OutputPath

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemplateFilePath
Specifies the path to the App-V package template file to be used for this package.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Expand-AppvSequencerPackage](./Expand-AppvSequencerPackage.md)

[New-AppvSequencerPackage](./New-AppvSequencerPackage.md)

