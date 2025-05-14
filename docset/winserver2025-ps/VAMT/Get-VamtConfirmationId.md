---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Licensing.VolumeActivation.Powershell.dll-Help.xml
Module Name: VAMT
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/vamt/get-vamtconfirmationid?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VamtConfirmationId
---

# Get-VamtConfirmationId

## SYNOPSIS
Acquires confirmation IDs (CIDs) from the Microsoft licensing servers during proxy activation.

## SYNTAX

### CilX (Default)
```
Get-VamtConfirmationId -FileName <String> [-ProxyUserName <String>] [-ProxyPassword <String>]
 [<CommonParameters>]
```

### Product
```
Get-VamtConfirmationId -Products <Product[]> [-ProxyUserName <String>] [-ProxyPassword <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-VamtConfirmationID** cmdlet acquires the confirmation IDs (CIDs) from the Microsoft licensing servers during proxy activation.
All products either in the Windows PowerShell object or in the .cilx file are updated with the results.

## EXAMPLES

### Example 1: Get CIDs from a file
```
PS C:\> Get-VamtConfirmationId -FileName "c:\users\me\desktop\vamtdata.cilx"
```

This command gets the CIDs for the products in the specified file.

### Example 2: Get CIDs for products
```
PS C:\> $ProductInfo = Get-VamtProduct
PS C:\> $UpdatedProductInfo = Get-VamtConfirmationId -Products $ProductInfo
```

This example gets a product object that has all products and gets the confirmation IDs for these products.

## PARAMETERS

### -FileName
Specifies the name of the file that contains the products that need CIDs.
Use this parameter during proxy activation to acquire CIDs for all products in the specified .cilx file.
You cannot use the *FileName* parameter together with the *Products* parameter.

```yaml
Type: String
Parameter Sets: CilX
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Products
Specifies the products in dep_nextref_vamt that need CIDs.
By default, if you do not specify a product, CIDs are retrieved for all products in dep_nextref_vamt.
You cannot use the *Products* parameter together with the *FileName* parameter.

```yaml
Type: Product[]
Parameter Sets: Product
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ProxyPassword
Specifies a password for a proxy server or gateway, if it is required for your environment.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ProxyUserName
```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-VamtProduct](./Get-VamtProduct.md)

[Install-VamtConfirmationId](./Install-VamtConfirmationId.md)

