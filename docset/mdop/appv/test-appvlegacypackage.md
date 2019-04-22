---
ms.technology: powershell-mdop
ms.mktglfcycl: manage
ms.author: kenwith
ms.prod: w10
ms.sitesec: library
author: kenwith
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.AppV.LegacyPackages.Module.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: 17DC65DC-3B04-43C3-94BA-21D049641D8E
ms.date: 2016-12-05
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Test-AppvLegacyPackage
---

# Test-AppvLegacyPackage

## SYNOPSIS
Validates App-V packages for conversion.

## SYNTAX

```
Test-AppvLegacyPackage [-SourcePath] <String[]> [<CommonParameters>]
```

## DESCRIPTION
The **Test-AppvLegacyPackage** cmdlet performs basic validation on Microsoft Application Virtualization (App-V) packages created by using an earlier version of App-V.
This cmdlet tests whether packages are compatible for conversion to the current App-V package format.

This cmdlet performs only basic validation, such as making sure that all files are present, and that the **ConvertFrom-AppvLegacyPackage** cmdlet supports the package version.
This validation does not guarantee success of a package conversion.

## EXAMPLES

### Example 1: Validate a package for conversion
```
PS C:\>Test-AppvLegacyPackage -SourcePath "C:\ContosoLegacyAppV"
```

This command validates whether an App-V package is compatible for conversion to the current App-V package format.

## PARAMETERS

### -SourcePath
Specifies an array of folders for the App-V packages that this cmdlet validates.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[ConvertFrom-AppvLegacyPackage](./ConvertFrom-AppvLegacyPackage.md)


