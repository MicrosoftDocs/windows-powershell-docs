---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.AppV.Modernizer.Cmdlets.dll-Help.xml
Module Name: AppvSequencer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/appvsequencer/new-appvpackageaccelerator?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-AppvPackageAccelerator
---

# New-AppvPackageAccelerator

## SYNOPSIS
Generates a package accelerator.

## SYNTAX

### FromInstaller (Default)
```
New-AppvPackageAccelerator [-InputPackagePath] <String> [-Installer] <String>
 [-AcceleratorDescriptionFile <String>] [-Path] <String> [<CommonParameters>]
```

### FromInstalledMedia
```
New-AppvPackageAccelerator [-InputPackagePath] <String> [-InstalledFilesPath] <String>
 [-AcceleratorDescriptionFile <String>] [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION
The **New-AppvPackageAccelerator** cmdlet generates a package accelerator object.
It accepts an existing Application Virtualization (App-V) 5.0 package file along with the appropriately installed files or installation media.
The cmdlet then generates a package accelerator file.

## EXAMPLES

### Example 1: Create a package accelerator
```
PS C:\> New-AppvPackageAccelerator -AppvPackageFilePath "C:\MyPackages\Package1\Package1.appv" -Installer "C:\MyPackages\Package1" -OutputPath "C:\Output\packages\Package1.cab"
```

This command creates a package accelerator using an installer folder containing, for example, MSI installers.

### Example 2: Create a package accelerator with instruction sheet
```
PS C:\> New-AppvPackageAccelerator -AppvPackageFilePath "C:\MyPackages\Package1\Package1.appv" -InstalledFilesPath "C:\Program Files\Package1InstallFolder" -OutputPath "C:\Output\packages\Package1.cab" -AcceleratorDescriptionFilePath "C:\MyPackages\Package1\Package1Description.rtf"
```

This command creates a package accelerator and inserts an instruction sheet on how to accelerate package.

## PARAMETERS

### -AcceleratorDescriptionFile
Specifies the package accelerator description file.

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

### -InputPackagePath
Specifies the path to the App-V package used as input to generate the accelerator from.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstalledFilesPath
Specifies the path to the folder containing the directory where the package is installed to, to generate an accelerator for.

```yaml
Type: String
Parameter Sets: FromInstalledMedia
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Installer
Specifies the path to the folder of the application installer to generate an accelerator from.
The installer must be of the format msi, or cab, or zip.
If you do not have an installer of this format, use the *InstalledFilesPath* parameter instead.

```yaml
Type: String
Parameter Sets: FromInstaller
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the full path to the .cab package accelerator output file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: OutputPath

Required: True
Position: 3
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

[Update-AppvSequencerPackage](./Update-AppvSequencerPackage.md)

