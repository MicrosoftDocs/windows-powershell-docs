---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.HardenedFabric.Cmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: ShieldedVMDataFile
ms.assetid: 94B371FC-5FD4-45FE-84E6-E9475B4DE8CF
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Import-ShieldingDataFile
ms.reviewer:
---

# Import-ShieldingDataFile

## SYNOPSIS
Imports shielding data.

## SYNTAX

```
Import-ShieldingDataFile [-ShieldingDataFilePath] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Import-ShieldingDataFile** cmdlet imports a **ShieldingDataFile** object from a shielding data file.

## EXAMPLES

### Example 1: Provision a virtual machine by using an imported data file
```
PS C:\>Import-ShieldingDataFile -ShieldingDataFilePath "ShieldingFile02.pdk" | Protect-ShieldingDataFile -ShieldingDataFilePath "ShieldingDataFile07.pdk"
```

This command creates a **ShieldingDataFile** object.
The command passes it to the Protect-ShieldingDataFile cmdlet.
That cmdlet specifies the output file name.

## PARAMETERS

### -ShieldingDataFilePath
Specifies the path of a shielding data file.
The file has the .pdk file name extension.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### ShieldingDataFile, ExistingVMShieldingDataFile
This cmdlet returns a **ShieldingDataFile** object.
This object represents a .pdk file used to provision a shielded virtual machine.

## NOTES

## RELATED LINKS

