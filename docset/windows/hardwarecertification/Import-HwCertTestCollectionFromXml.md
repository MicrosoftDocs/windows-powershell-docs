---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: microsoft.windows.kits.hardware.certification.management.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Import-HwCertTestCollectionFromXml
ms.reviewer:
ms.assetid: A5BFF242-9450-4678-B8D0-032094077D30
---

# Import-HwCertTestCollectionFromXml

## SYNOPSIS
Imports a test collection from an .xml file.

## SYNTAX

```
Import-HwCertTestCollectionFromXml [-LiteralPath] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Import-HwCertTestCollectionFromXml** cmdlet imports a test collection from an .xml file.
For more information, see [Windows Hardware Certification Kit downloads](http://go.microsoft.com/fwlink/?LinkId=614978) in the Microsoft Developer Network (MSDN) Library.

After you import a test collection, you can filter it by using **TestCollectionRecord** properties, and then use the **Export-HwCertTestCollectionToXml** cmdlet to export the filtered test collection.

## EXAMPLES

### Example 1: Filter a test collection
```
PS C:\> Import-HwCertTestCollectionFromXml -Input "C:\Temp\All.xml" | Where-Object { $_.ContentLevelSet.Contains("Basic") }
```

This command imports a test collection, and then finds the results that belong to a specified content level.
The command imports a test collection named All.xml, as a **TestCollectionRecord** object, and then passes that object to the **Where-Object** cmdlet by using the pipeline operator.
The **Where-Object** cmdlet filters the imported object for results that belong to the Basic content level.
For more information, type `Get-Help Where-Object`.

### Example 2: Filter a test collection and export the results to a new test collection
```
PS C:\> Import-HwCertTestCollectionFromXml -Input "C:\Temp\All.xml" | Where-Object { $_.ContentLevelSet.Contains("Basic") } | Export-HwCertTestCollectionToXml -Output "C:\Temp\Basic.xml"
```

This command imports a test collection, finds the results that belong to a specified content level, and exports a new test collection .xml file that contains only those results.
The command imports a test collection named All.xml, as a **TestCollectionRecord** object, and then passes that object to the **Where-Object** cmdlet by using the pipeline operator.
The **Where-Object** cmdlet filters the imported object for results that belong to the Basic content level.
For more information, type `Get-Help Where-Object`.
The command then passes those items to the **Export-HwCertTestCollectionToXml** cmdlet, which exports the test collection to the file named Basic.xml.

## PARAMETERS

### -LiteralPath
Specifies a full path.
This is the file path to the test collection .xml file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: XML, Input, Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Export-HwCertTestCollectionToXml](./Export-HwCertTestCollectionToXml.md)

