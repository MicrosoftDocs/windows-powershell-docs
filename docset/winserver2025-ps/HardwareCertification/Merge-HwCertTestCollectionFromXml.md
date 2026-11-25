---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: microsoft.windows.kits.hardware.certification.management.dll-Help.xml
Module Name: HardwareCertification
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hardwarecertification/merge-hwcerttestcollectionfromxml?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Merge-HwCertTestCollectionFromXml
---

# Merge-HwCertTestCollectionFromXml

## SYNOPSIS
Merges test result information from several test collection files into a single test collection.

## SYNTAX

```
Merge-HwCertTestCollectionFromXml [-LiteralPath] <String[]> [-ValidationXmlPath <String>]
 [-HckBuildVersion <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Merge-HwCertTestCollectionFromXml** cmdlet merges test result information from several test collection .xml files into a single test collection.
For more information, see [Windows Hardware Certification Kit downloads](https://go.microsoft.com/fwlink/?LinkId=614978) in the Microsoft Developer Network (MSDN) Library.

You can use the **Export-HwCertTestCollectionToXml** cmdlet to export the merged test collection as an .xml file.
You can use the **New-HwCertTestCollectionExcelReport** cmdlet to create a Microsoft Excel report of the test results.

## EXAMPLES

### Example 1: Merge two test collection files
```
PS C:\> Merge-HwCertTestCollectionFromXml -LiteralPath ("C:\Temp\BasicTest.xml", "C:\Temp\CertificationTest.xml")
```

This command merges the results in two test collection files.
The command specifies files named BasicTest.xml and CertificationTest.xml.

### Example 2: Merge two test collection files and export the result information
```
PS C:\> Merge-HwCertTestCollectionFromXml -LiteralPath ("C:\Temp\BasicTest.xml", "C:\Temp\CertificationTest.xml") | Export-HwCertTestCollectionToXml -Output "C:\Temp\Merged.xml"
```

This command merges the results in two test collection files and exports the test result information to an .xml file named Merged.xml.
The command merges files named BasicTest.xml and CertificationTest.xml.
The command then passes the merged results to the **Export-HwCertTestCollectionToXml** cmdlet by using the pipeline operator.
That cmdlet exports the results.

### Example 3: Merge several test collection files and export the result information
```
PS C:\> Get-ChildItem -Recurse "C:\Temp\*.xml" | Merge-HwCertTestCollectionFromXml | Export-HwCertTestCollectionToXml -Output "C:\Temp\Merged.xml"
```

This command merges the results in all the test collection files in a specified folder and exports the merged test result information to an .xml file named Merged.xml.
The command uses the **Get-ChildItem** cmdlet to get all the .xml files in the C:\Temp folder.
For more information, type `Get-Help Get-ChildItem`.
The command then passes the .xml files to the **Merge-HwCertTestCollectionFromXml** cmdlet by using the pipeline operator.
That cmdlet merges the test results.
Finally, the command passes the merged results to the **Export-HwCertTestCollectionToXml** cmdlet.
That cmdlet exports the results.

## PARAMETERS

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

### -LiteralPath
Specifies an array of file paths.
These are file paths to test collection .xml files.

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

### Microsoft.Windows.Kits.Hardware.Certification.TestCollectionRecord

## NOTES

## RELATED LINKS

[Export-HwCertTestCollectionToXml](./Export-HwCertTestCollectionToXml.md)

[Merge-HwCertTestCollectionFromPackage](./Merge-HwCertTestCollectionFromPackage.md)

[New-HwCertTestCollection](./New-HwCertTestCollection.md)

