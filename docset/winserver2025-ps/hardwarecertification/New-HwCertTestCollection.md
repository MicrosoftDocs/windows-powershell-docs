---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: microsoft.windows.kits.hardware.certification.management.dll-Help.xml
Module Name: HardwareCertification
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hardwarecertification/new-hwcerttestcollection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-HwCertTestCollection
---

# New-HwCertTestCollection

## SYNOPSIS
Creates a test collection file from a project definition file.

## SYNTAX

```
New-HwCertTestCollection [-ProjectDefinitionFile] <String> [<CommonParameters>]
```

## DESCRIPTION
The **New-HwCertTestCollection** cmdlet creates a test collection file from a Windows Hardware Certification Kit (HCK) project definition file.
The collection file represents the testing scope of a unique combination of test and target and version of the Windows operating system.
For more information, see [Windows Hardware Certification Kit downloads](https://go.microsoft.com/fwlink/?LinkId=614978) in the Microsoft Developer Network (MSDN) Library.

You can use this test collection file in several ways at different stages of the testing workflow, including the following:

- Generate an initial test collection to understand the full scope of testing.
- Filter the test collection based on test metadata and properties, and then generate smaller collections for different labs to run.
- Use a test collection with results to control the scope of testing.
For instance, the tests could skip all passing tests.
- Use a test collection as a validation file when you merge test results from the smaller collections.

The cmdlet creates temporary projects and target families to enumerate all the possible tests.
You can reuse the generated project for additional testing outside of the automation workflow by using tools from the HCK.

Use the **New-HwCertProjectDefinitionFile** cmdlet to create a project definition file.

## EXAMPLES

### Example 1: Create a test collection
```
PS C:\> New-HwCertTestCollection -ProjectDefinitionFile "C:\Temp\ProjectDefinitionWindows8Client.xml"
```

This command creates a test collection based on the project definition file named ProjectDefinitionWindows8Client.xml.

### Example 2: Create a test collection and export it to a file
```
PS C:\> New-HwCertTestCollection -ProjectDefinitionFile "C:\Temp\ProjectDefinitionWindows8Client.xml" | Export-HwCertTestCollectionToXml -Output "C:\Temp\TestCollectionWindows8Client.xml"
```

This command creates a test collection and then exports it to an .xml file.
This command creates a test collection based on the project definition file named ProjectDefinitionWindows8Client.xml, and then passes the test collection to the **Export-HwCertTestCollectionToXml** cmdlet by using the pipeline operator.
That cmdlet exports it to a file called TestCollectionWindows8Client.xml.

## PARAMETERS

### -ProjectDefinitionFile
Specifies the project definition file as a full path.
To create a project definition file, use the **New-HwCertProjectDefinitionFile** cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Input, PDF, Project

Required: True
Position: 0
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

[New-HwCertProjectDefinitionFile](./New-HwCertProjectDefinitionFile.md)

