---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Licensing.VolumeActivation.Powershell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Install-VamtConfirmationId
ms.reviewer:
ms.assetid: AA1552D8-C032-4343-96F7-DF498D9F0E36
---

# Install-VamtConfirmationId

## SYNOPSIS
Installs Confirmation IDs (CID) acquired from Microsoft to the respective computers to complete proxy activation.

## SYNTAX

```
Install-VamtConfirmationId -Products <Product[]> [-Username <String>] [-Password <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Install-VamtConfirmationID** cmdlet installs the confirmation IDs (CIDs) to the computers in the system and alerts the products that they have been enabled.
Use this cmdlet for proxy activations after you have acquired the CIDs from the Microsoft licensing servers.

## EXAMPLES

### Example 1: Install CIDs in the database
```
PS C:\> Import-VamtData -InputFile "c:\users\me\desktop\vamtdata.cilx"
PS C:\> $ProductInfo = Get-VamtProduct
PS C:\> $UpdatedProductInfo = Install-VamtConfirmationID -Products $ProductInfo
PS C:\> Import-VamtData -Products $UpdatedProductInfo
```

This command imports a file and acquires the data in the file.
It then installs the CIDs to the dep_nextref_vamt data object.
Finally, it imports the dep_nextref_vamt data object into the dep_nextref_vamt database.
Run this command at the end of a proxy activation.

## PARAMETERS

### -Password
Provides a password for password-protected environments.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Products
Specifies the product or products to install the CIDs on during the proxy activation process.

```yaml
Type: Product[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Username
Provides a user name for password-protected environments.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-VamtConfirmationId](./Get-VamtConfirmationId.md)

[Get-VamtProduct](./Get-VamtProduct.md)

[Import-VamtData](./Import-VamtData.md)

