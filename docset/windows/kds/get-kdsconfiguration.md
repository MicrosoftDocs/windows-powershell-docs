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
title: Get-KdsConfiguration
ms.reviewer:
ms.assetid: 7ED02CD3-B127-4EA4-9625-8D6FF3141E54
---

# Get-KdsConfiguration

## SYNOPSIS
Retrieves the current configuration of the Microsoft Group KdsSvc from Active Directory.

## SYNTAX

```
Get-KdsConfiguration [<CommonParameters>]
```

## DESCRIPTION
The **Get-KdsConfiguration** cmdlet retrieves the current configuration of the Microsoft Group Key Distribution Service (KdsSvc) from Active Directory.
The KDS configuration defines how keys are generated from the root keys.

## EXAMPLES

### Example 1: Retrieve the current KDS configuration
```
PS C:\> Get-KdsConfiguration
```

This command retrieves the current configuration of the Microsoft Group KdsSvc from Active Directory.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
This cmdlet accepts no input objects.

## OUTPUTS

### Microsoft.KeyDistributionService.KdsServerConfiguration
This cmdlet returns a **KdsServerConfiguration** object contains information such as the key derivation function (KDF) algorithm and secret agreement algorithm used in key generation.

## NOTES

## RELATED LINKS

[Add-KdsRootKey](./Add-KdsRootKey.md)

[Clear-KdsCache](./Clear-KdsCache.md)

[Get-KdsRootKey](./Get-KdsRootKey.md)

[Set-KdsConfiguration](./Set-KdsConfiguration.md)

[Test-KdsRootKey](./Test-KdsRootKey.md)

