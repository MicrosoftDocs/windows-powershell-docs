---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ShieldedVmCmdlets-help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: ShieldedVMProvisioning
ms.assetid: B9082BC5-6746-468E-BEA4-887DCDE27F5B
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology:
ms.topic: reference
online version:
schema: 2.0.0
title: Get-KeyProtectorFromShieldingDataFile
ms.reviewer:
---

# Get-KeyProtectorFromShieldingDataFile

## SYNOPSIS
Gets the Key Protector from a Shielding Data File.

## SYNTAX

```
Get-KeyProtectorFromShieldingDataFile [-ShieldingDataFilePath] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-KeyProtectorFromShieldingDataFile** cmdlet gets the Key Protector from a Shielding Data File.

## EXAMPLES

### Example 1: Extract the raw byte form of the Key Protector from the shielding data file
```
PS C:\>Get-KeyProtectorFromShieldingDataFile -ShieldingDataFilePath "C:\temp\shieldingdata.pdk"
0 0 36 52 [...]
```

This command extracts the raw byte form of the key protector from the shielding data file located at C:\temp\shieldingdata.pdk

### Example 2: Extract the raw key protector from the shielding data and convert it to an HGS Key Protector object
```
PS C:\>$KP = Get-KeyProtectorFromShieldingDataFile -ShieldingDataFilePath 'C:\temp\shieldingdata.pdk'
PS C:\> ConvertTo-HgsKeyProtector -Bytes $KP
```

The first command extracts the raw key protector from the shielding data file located at C:\temp\shieldingdata.pdk and stores the result in the variable named $KP.

The second command converts raw key protector stored in the $KB variable to an HGS Key Protector object for further inspection.

## PARAMETERS

### -ShieldingDataFilePath
Specifies the location of a Shielding Data File (.pdk).

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Byte[]

This cmdlet returns a Byte\[\] array that represents the raw key protector structure.

## NOTES

## RELATED LINKS

[Shielded Virtual Machine Provisioning Cmdlets in Windows PowerShell](./shieldedvmcmdlets.md)
