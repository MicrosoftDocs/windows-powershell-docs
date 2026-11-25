---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: microsoft.windows.kits.hardware.certification.management.dll-Help.xml
Module Name: HardwareCertification
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hardwarecertification/new-hwcerttestcollectionexcelreport?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-HwCertTestCollectionExcelReport
---

# New-HwCertTestCollectionExcelReport

## SYNOPSIS
Creates an HCK test summary report.

## SYNTAX

```
New-HwCertTestCollectionExcelReport [-LiteralPath] <String[]> -ExcelPath <String> -ResultCount <Int32>
 [<CommonParameters>]
```

## DESCRIPTION
The **New-HwCertTestCollectionExcelReport** cmdlet creates a Windows Hardware Certification Kit (HCK) test summary report as a Microsoft Excel workbook.
Specify one or more merged test collection .xml files.
The cmdlet creates a separate worksheet for each merged test collection file, aggregates results, and compares the same test target from each file in a summary report.
The summary shows total pass, pass with filter, fail, and N-1 regression data.
For more information, see [Windows Hardware Certification Kit downloads](https://go.microsoft.com/fwlink/?LinkId=614978) in the Microsoft Developer Network (MSDN) Library.

You can use up to ten results per test in the test result aggregation process.
The most recent passing result takes precedence as the aggregate.

The maximum number of test collections for a summary report is eight.
If you specify a single merged test collection, the report includes the summary for that test pass without N-1 regression comparisons.

To create merged test result collection files, use the **Merge-HwCertTestCollectionFromPackage** and **Merge-HwCertTestCollectionFromXml** cmdlets, along with the **Export-HwCertTestCollectionToXml** cmdlet.

## EXAMPLES

### Example 1: Create a report for two merged test collections
```
PS C:\> New-HwCertTestCollectionExcelReport -LiteralPath ("C:\Temp\Merged_TP001.xml", "C:\Temp\Merged_TP002.xml") -ExcelPath "C:\Temp\Report.xls" -ResultCount 1
```

This command creates an Excel report from two merged test collection .xml files from two test passes.
The command specifies a report count value of one.

## PARAMETERS

### -ExcelPath
Specifies a full path for the new Excel report.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LiteralPath
Specifies an array of full paths.
These are file paths to merged test collection .xml files.
You can specify up to eight files.

The cmdlet uses the order of the files in this parameter to determine the order of the N-1 regression data comparison.
For example, the second file is compared with the first file, and the third file is compared with the second file.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Input, MergedCollection

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResultCount
Specifies the number of results.
The cmdlet reports on these results and uses these results in the result aggregate process.
The maximum value is ten.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: True
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

[Merge-HwCertTestCollectionFromPackage](./Merge-HwCertTestCollectionFromPackage.md)

[Merge-HwCertTestCollectionFromXml](./Merge-HwCertTestCollectionFromXml.md)

[Export-HwCertTestCollectionToXml](./Export-HwCertTestCollectionToXml.md)

