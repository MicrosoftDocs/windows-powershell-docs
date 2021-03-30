---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Licensing.VolumeActivation.Powershell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Install-VamtProductActivation
ms.reviewer:
ms.assetid: 5B87C8DB-4B08-4C82-BBB9-E17C75EFB79D
---

# Install-VamtProductActivation

## SYNOPSIS
Activates products online, using the local computer's Internet connection.

## SYNTAX

```
Install-VamtProductActivation -Products <Product[]> [-Username <String>] [-Password <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Install-VamtProductActivation** cmdlet activates products online by using the Internet connection on the local computer.
You cannot use this cmdlet for proxy activation.

## EXAMPLES

### Example 1: Activate products
```
PS C:\>Get-VamtProduct | Install-VamtProductActivation
```

This command gets products and then activates them by using online activation.

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
Specifies the product or products to be activated.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-VamtProduct](./Get-VamtProduct.md)

