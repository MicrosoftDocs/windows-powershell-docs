---
ms.technology: 
ms.mktglfcycl: manage
ms.author: v-kaunu
ms.prod: w10
ms.sitesec: library
author: Kateyanne
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.AppV.Modernizer.Cmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: 55F31C69-B695-4EE0-860D-65E78B95DE0E
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: New-AppvPackageAccelerator
---

# New-AppvPackageAccelerator

## SYNOPSIS
Generates a new package accelerator.

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
The **New-AppvPackageAccelerator** cmdlet generates a new package accelerator object.
It accepts an existing Application Virtualization (App-V) 5.0 package file along with the appropriately installed files or install media.
The cmdlet then generates a package accelerator file.

## EXAMPLES

### Example 1: Create a package accelerator
```
PS C:\> New-AppvPackageAccelerator -AppvPackageFilePath "C:\MyPackages\Package1\Package1.appv" -Installer "C:\MyPackages\Package1" -OutputPath "C:\Output\packages\Package1.cab"
```

This command creates a package accelerator using an installer folder containing, for example, Windows Installer packages.

### Example 2: Create a package accelerator with instruction sheet
```
PS C:\> New-AppvPackageAccelerator -AppvPackageFilePath "C:\MyPackages\Package1\Package1.appv" -InstalledFilesPath "C:\Program Files\Package1InstallFolder" -OutputPath "C:\Output\packages\Package1.cab" -AcceleratorDescriptionFilePath "C:\MyPackages\Package1\Package1Description.rtf"
```

This command creates a package accelerator and inserts an instruction sheet on how to accelerate package.

## PARAMETERS

### -AcceleratorDescriptionFile
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
The installer must be an .msi file, or .cab file, or .zip file.
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


