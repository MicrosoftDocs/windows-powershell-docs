---
ms.technology: 
ms.mktglfcycl: manage
ms.author: v-kaunu
ms.prod: w10
ms.sitesec: library
author: Kateyanne
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.AppV.LegacyPackages.Module.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: 40230EE3-784C-4429-AAF0-D56ABDDF988B
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: ConvertFrom-AppvLegacyPackage
---

# ConvertFrom-AppvLegacyPackage

## SYNOPSIS
Converts App-V packages to the format for the current version of App-V.

## SYNTAX

```
ConvertFrom-AppvLegacyPackage [-SourcePath] <String[]> [-DestinationPath] <String>
 [-DownloadFullPackageOnFirstLaunch] [-OSDsToIncludeInPackage <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **ConvertFrom-AppvLegacyPackage** cmdlet converts Microsoft Application Virtualization (App-V) packages created by using an earlier version of App-V.
This cmdlet converts packages to the format that works with the current version of App-V.
The cmdlet returns all packages that it successfully converts, and it returns error or warning messages that it produces while it converts packages.

## EXAMPLES

### Example 1: Convert a package
```
PS C:\>ConvertFrom-AppvLegacyPackage -SourcePath "C:\ContosoLegacyAppV" -DestinationPath "C:\ContosoAppV50"
```

This command converts a single App-V package in a previous format to the current App-V format.

### Example 2: Convert all packages under a folder
```
PS C:\>$Packages = ,$Null
PS C:\> Foreach($x in (Get-ChildItem -recurse)) { if($x.FullName.EndsWith("sprj")) { $Packages += $x.PSParentPath } }
PS C:\> ConvertFrom-AppvLegacyPackage -SourcePath $Packages
```

The first command creates an empty array named $Packages.

The second command uses the **ForEach**Windows PowerShell® language command to check recursively for files that have an .sprj file name extension.
The command stores all the folders that contain .sprj files in the $Packages array.

The final command converts each package stored in $Packages to the current App-V format.

## PARAMETERS

### -DestinationPath
Specifies the folder where this cmdlet stores the converted packages.

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

### -DownloadFullPackageOnFirstLaunch
Indicates that you should fully download the converted package before you start it, instead of streaming it.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: FullLoad

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OSDsToIncludeInPackage
Specifies an array of Open Software Descriptors (OSDs) that contain information that this cmdlet includes in the converted App-V package.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: OSDs

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourcePath
Specifies an array of folders for the App-V packages that this cmdlet converts.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Path, PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Test-AppvLegacyPackage](./Test-AppvLegacyPackage.md)


