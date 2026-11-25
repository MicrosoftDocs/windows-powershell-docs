---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: microsoft.windows.kits.hardware.certification.management.dll-Help.xml
Module Name: HardwareCertification
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hardwarecertification/merge-hwcerttestcollectionfrompackage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Merge-HwCertTestCollectionFromPackage
---

# Merge-HwCertTestCollectionFromPackage

## SYNOPSIS
Merges test result information from several .hckx package files into a single test collection.

## SYNTAX

```
Merge-HwCertTestCollectionFromPackage [-LiteralPath] <String[]> [-Force] [-IncludeAll]
 [-ValidationXmlPath <String>] [-HckBuildVersion <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Merge-HwCertTestCollectionFromPackage** cmdlet merges the test result information from several .hckx package files into a single test collection.
For more information, see [Windows Hardware Certification Kit downloads](https://go.microsoft.com/fwlink/?LinkId=614978) in the Microsoft Developer Network (MSDN) Library.

You can use the **Export-HwCertTestCollectionToXml** cmdlet to export the merged test collection as an .xml file.
You can use the **New-HwCertTestCollectionExcelReport** cmdlet to create a Microsoft Excel report of the test results.

The cmdlet parses each .hckx package file, and then generates a cached .xml file in the same location as each parsed file.
Therefore, you must have write permission for the folders that contain the .hckx package files.

## EXAMPLES

### Example 1: Merge two package files
```
PS C:\> Merge-HwCertTestCollectionFromPackage -LiteralPath ("C:\Temp\BasicTest.hckx", "C:\Temp\CertificationTest.hckx")
```

This command merges the results in two .hckx package files.
The command specifies files named BasicTest.hckx and CertificationTest.hckx.

### Example 2: Merge two package files and export the result information
```
PS C:\> Merge-HwCertTestCollectionFromPackage -LiteralPath ("C:\Temp\BasicTest.hckx", "C:\Temp\CertificationTest.hckx") | Export-HwCertTestCollectionToXml -Output "C:\Temp\Merged.xml"
```

This command merges the results in two .hckx package files and exports the result information to an .xml file named Merged.xml.
The command merges files named BasicTest.hckx and CertificationTest.hckx.
The command passes the merged results to the **Export-HwCertTestCollectionToXml** cmdlet by using the pipeline operator.
That cmdlet exports the results.

### Example 3: Merge several package files and export the result information
```
PS C:\> Get-ChildItem -Recurse "C:\Temp\*.hckx" | Merge-HwCertTestCollectionFromPackage | Export-HwCertTestCollectionToXml -Output "C:\Temp\Merged.xml"
```

This command merges the results in all the .hckx package files in a specified folder and exports the merged result information to an .xml file named Merged.xml.
The command uses the **Get-ChildItem** cmdlet to get all the .hckx files in the C:\Temp folder.
For more information, type `Get-Help Get-ChildItem`.
The command passes the .hckx files to the **Merge-HwCertTestCollectionFromXml** cmdlet by using the pipeline operator.
That cmdlet merges the test results.
The command then passes the merged results to the **Export-HwCertTestCollectionToXml** cmdlet.
That cmdlet exports the results.

## PARAMETERS

### -Force
Indicates that the cmdlet parses the .hckx package files, and then replaces any existing cached .xml files.

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

### -HckBuildVersion
Specifies an HCK build version.
This cmdlet merges the results that match this build version only.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Build, Version

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeAll
If specified, the merge includes all test results, including any that passed, and any that failed, such as those with "not-run" results.

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

### -LiteralPath
Specifies an array of file paths.
These are file paths to .hckx package files.
You must have write permission for the folders that contain these files.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ValidationXmlPath
Specifies the path of a test collection .xml file to use for validation.
The cmdlet checks the new test collection against the validation collection to ensure that at least one result exists.
Validation helps to determine that all the tests merged from child lab collections meet the goals of the original test collection.

To obtain a test collection file for validation, use the **New-HwCertTestCollection** cmdlet, along with the **Export-HwCertTestCollectionToXml** cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: XML

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

[Export-HwCertTestCollectionToXml](./Export-HwCertTestCollectionToXml.md)

[Merge-HwCertTestCollectionFromXml](./Merge-HwCertTestCollectionFromXml.md)

