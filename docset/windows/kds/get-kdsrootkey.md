---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.KeyDistributionService.Cmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-KdsRootKey
ms.reviewer:
ms.assetid: EA11EBE8-C5AB-42B5-AF52-903CD262849F
---

# Get-KdsRootKey

## SYNOPSIS
Retrieves a list of root key values stored by the Microsoft Group KdsSvc.

## SYNTAX

```
Get-KdsRootKey [<CommonParameters>]
```

## DESCRIPTION
The **Get-KdsRootKey** cmdlet retrieves the following information from Active Directory for each root key: 

- The root key identifier 
- The root key value 
- The Microsoft Group Key Distribution Service (KdsSvc)

This information is required to generate the group keys distributed by the Microsoft Group KdsSvc.

## EXAMPLES

### Example 1: Retrieve a list of root key values
```
PS C:\> Get-KdsRootKey
```

This command retrieves a list of root key values stored in Active Directory.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
This cmdlet accepts no input objects.

## OUTPUTS

### System.Collections.Generic.List`1<KdsRootKey^>
This cmdlet returns a list of master root keys stored in Active Directory.

## NOTES

## RELATED LINKS

[Add-KdsRootKey](./Add-KdsRootKey.md)

[Clear-KdsCache](./Clear-KdsCache.md)

[Get-KdsConfiguration](./Get-KdsConfiguration.md)

[Set-KdsConfiguration](./Set-KdsConfiguration.md)

[Test-KdsRootKey](./Test-KdsRootKey.md)

