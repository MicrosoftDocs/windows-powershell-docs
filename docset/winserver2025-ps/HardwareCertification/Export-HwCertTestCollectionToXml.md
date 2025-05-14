---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: microsoft.windows.kits.hardware.certification.management.dll-Help.xml
Module Name: HardwareCertification
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hardwarecertification/export-hwcerttestcollectiontoxml?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-HwCertTestCollectionToXml
---

# Export-HwCertTestCollectionToXml

## SYNOPSIS
Exports a test collection to an .xml file.

## SYNTAX

```
Export-HwCertTestCollectionToXml [-InputObject] <TestCollectionRecord[]> -Output <String>
 [-TestPassIdentifier <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Export-HwCertTestCollectionToXml** cmdlet exports a test collection to an .xml file.
For more information, see [Windows Hardware Certification Kit downloads](https://go.microsoft.com/fwlink/?LinkId=614978) in the Microsoft Developer Network (MSDN) Library.

After you export a test collection, you can use the **Merge-HwCertTestCollectionFromXml** cmdlet to merge it with other test collections.
Use the **Import-HwCertTestCollectionFromXml** cmdlet to import test collections that you previously exported.
After you import a test collection, you can filter it by using **TestCollectionRecord** properties, and then use this cmdlet to export the filtered test collection.

## EXAMPLES

### Example 1: Filter a test collection
```
PS C:\> Import-HwCertTestCollectionFromXml -Input "C:\Temp\All.xml" | Where-Object { $_.ContentLevelSet.Contains("Basic") } | Export-HwCertTestCollectionToXml -Output "C:\Temp\Basic.xml"
```

This command imports a test collection, finds the results that belong to a specified content level, and exports a new test collection .xml file that contains only those results.
The command uses the **Import-HwCertTestCollectionFromXml** cmdlet to import a test collection named All.xml, as a **TestCollectionRecord** object, and then passes that object to the **Where-Object** cmdlet by using the pipeline operator.
The **Where-Object** cmdlet filters the imported object for results belong to the Basic content level.
For more information, type `Get-Help Where-Object`.
The command passes those items to the **Export-HwCertTestCollectionToXml** cmdlet, which exports the test collection to the file named Basic.xml.

## PARAMETERS

### -InputObject
Specifies an array of **TestCollectionRecord** objects.
To obtain a **TestCollectionRecord** object, use the **New-HwCertTestCollection** cmdlet.
You can also use the **Merge-HwCertTestCollectionFromXml** cmdlet or the **Merge-HwCertTestCollectionFromPackage** cmdlet to obtain merged results, as a **TestCollectionRecord** object.

```yaml
Type: TestCollectionRecord[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Output
Specifies a full path for the exported file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Path

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TestPassIdentifier
Specifies a case-sensitive identifier that you assign to the exported test collection.

```yaml
Type: String
Parameter Sets: (All)
Aliases: TP, ID

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

[Import-HwCertTestCollectionFromXml](./Import-HwCertTestCollectionFromXml.md)

[New-HwCertTestCollection](./New-HwCertTestCollection.md)

[Merge-HwCertTestCollectionFromXml](./Merge-HwCertTestCollectionFromXml.md)

[Merge-HwCertTestCollectionFromPackage](./Merge-HwCertTestCollectionFromPackage.md)

