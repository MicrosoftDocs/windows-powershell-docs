---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ShieldedVmCmdlets-help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: ShieldedVMProvisioning
ms.assetid: 1817F913-D586-4926-96C5-766DAD08C004
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: New-ShieldedVMSpecializationDataFile
ms.reviewer:
---

# New-ShieldedVMSpecializationDataFile

## SYNOPSIS
Creates a specialization data file to be used when provisioning a shielded virtual machine.

## SYNTAX

```
New-ShieldedVMSpecializationDataFile [-ShieldedVMSpecializationDataFilePath] <String>
 [-SpecializationDataPairs] <Hashtable> [<CommonParameters>]
```

## DESCRIPTION
The **New-ShieldedVMSpecializationDataFile** cmdlet creates a specialization data file to be used when provisioning a shielded virtual machine.

## EXAMPLES

### Example 1: Create a specialization data file to be used when provisioning a shielded virtual machine
```
PS C:\>New-ShieldedVMSpecializationDataFile -ShieldedVMSpecializationDataFilePath "C:\temp\VM01.fsk" -SpecializationDataPairs @{ "@ComputerName@" = "PC-001"; "@TimeZone@" = "GMT Standard Time" }
```

This command creates a specialization data file mapping the string @ComputerName@ in answer files to PC-001 and @TimeZone@ to GMT Standard Time.
The file is stored at C:\temp\VM01.fsk.

## PARAMETERS

### -ShieldedVMSpecializationDataFilePath
Specifies the path where the specialization data file (.fsk) is saved.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SpecializationDataPairs
Specifies a table of key-value pairs used to replace strings in the answer file.
The values must be strings.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-KeyProtectorFromShieldingDataFile](./Get-KeyProtectorFromShieldingDataFile.md)

[Get-ShieldedVMProvisioningStatus](./Get-ShieldedVMProvisioningStatus.md)

[Initialize-ShieldedVM](./Initialize-ShieldedVM.md)

[Test-ShieldingDataApplicability](./Test-ShieldingDataApplicability.md)

