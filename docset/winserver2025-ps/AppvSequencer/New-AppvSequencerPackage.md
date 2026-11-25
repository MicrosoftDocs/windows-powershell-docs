---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.AppV.Modernizer.Cmdlets.dll-Help.xml
Module Name: AppvSequencer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/appvsequencer/new-appvsequencerpackage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-AppvSequencerPackage
---

# New-AppvSequencerPackage

## SYNOPSIS
Creates a new App-V package.

## SYNTAX

### ByInstallerFullLoad (Default)
```
New-AppvSequencerPackage [-FullLoad] [-Installer] <String[]> [-InstallerOptions <String[]>]
 [[-PrimaryVirtualApplicationDirectory] <String>] [-Name] <String> [-Path] <String>
 [-TemplateFilePath <String>] [<CommonParameters>]
```

### ByPackageAcceleratorInstallMedia
```
New-AppvSequencerPackage [-AcceleratorFilePath] <String> [-InstallMediaPath] <String> [-Name] <String>
 [-Path] <String> [<CommonParameters>]
```

### ByPackageAcceleratorInstalledFiles
```
New-AppvSequencerPackage [-AcceleratorFilePath] <String> [-InstalledFilesPath] <String> [-Name] <String>
 [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION
The **New-AppvSequencerPackage** cmdlet creates a new Microsoft Application Virtualization (App-V) package, either using an installer, an App-V accelerator, or an accelerator with an installed application.
The cmdlet accepts a template file, as well as the option to force the package to be fully streamed to the computer before running the package.

## EXAMPLES

### Example 1: Create a package
```
PS C:\> New-AppvSequencerPackage -Name "MyPackage" -OutputPath "C:\MyPackage" -PrimaryVirtualApplicationDirectory "C:\Program Files\MyApp" -Installer "C:\installers\MyApp\setup.exe"
```

This command creates a package for the application MyApp.

### Example 2: Create a package that must be fully downloaded
```
PS C:\> New-AppvSequencerPackage -Name MyPackage2 -OutputPath C:\MyPackages -PrimaryVirtualApplicationDirectory "C:\Program Files\MyApp -Installer C:\installers\MyApp\setup.exe -FullLoad
```

This command creates a package that must be fully downloaded for the application MyApp.

### Example 3: Create a package using a pre-generated accelerator
```
PS C:\> New-AppvSequencerPackage -Name "MyPackage" -OutputPath "C:\MyPackages" -AcceleratorFilePath "C:\MyAccelerators\MyAccelerator.cab" -PrimaryVirtualApplicationDirectory "C:\MyApp\" -InstalledMediaPath "C:\Installers\PreReq\" -Installer "C:\Installers\MyApp\setup.exe"
```

This command creates a new package MyApp using a pre-generated package accelerator.

### Example 4: Create a package using a template file
```
PS C:\> New-AppvSequencerPackage -Name "MyPackage" -TemplateFilePath "C:\template.appvt" -OutputPath "C:\Packages\MyPackage" -PrimaryVirtualApplicationDirectory "C:\Program Files\MyApp" -Installer "C:\Installers\MyApp\setup.exe"
```

This command creates a new MyApp package using a template file.

## PARAMETERS

### -AcceleratorFilePath
Specifies the path to the accelerator file for this package.
If the accelerator is not signed or is not accepted by the Sequencer, an error is returned.

```yaml
Type: String
Parameter Sets: ByPackageAcceleratorInstallMedia, ByPackageAcceleratorInstalledFiles
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullLoad
Indicates that the package is required to be fully downloaded before being launched.

```yaml
Type: SwitchParameter
Parameter Sets: ByInstallerFullLoad
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstalledFilesPath
Specifies the location of the already installed files used to create a new App-V package with the aid of an App-V Accelerator.

```yaml
Type: String
Parameter Sets: ByPackageAcceleratorInstalledFiles
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Installer
Specifies a collection of MSIs, setup executables, or other executables needed to be run to create the App-V package.

```yaml
Type: String[]
Parameter Sets: ByInstallerFullLoad
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstallerOptions
Specifies an array of Installer Command-Line Options as parameter values, such as /quiet, /passive, or /norestart.

```yaml
Type: String[]
Parameter Sets: ByInstallerFullLoad
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstallMediaPath
Specifies the location of the installation media that the Sequencer points to and generates an accelerator.

```yaml
Type: String
Parameter Sets: ByPackageAcceleratorInstallMedia
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the App-V package.
This is also the name of all files outputted by the sequencing process.

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

### -Path
Specifies the folder where the package is saved.

```yaml
Type: String
Parameter Sets: (All)
Aliases: OutputPath

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryVirtualApplicationDirectory
Specifies the location where the application is being installed.
This must be a path on the local computer.

```yaml
Type: String
Parameter Sets: ByInstallerFullLoad
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemplateFilePath
Specifies the path to the App-V package template file to be used for this package.

```yaml
Type: String
Parameter Sets: ByInstallerFullLoad
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

[New-AppvPackageAccelerator](./New-AppvPackageAccelerator.md)

[Update-AppvSequencerPackage](./Update-AppvSequencerPackage.md)

