---
external help file: Microsoft.KeyDistributionService.Cmdlets.dll-Help.xml
Module Name: Kds
online version: 
schema: 2.0.0
title: Get-KdsConfiguration
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 7ED02CD3-B127-4EA4-9625-8D6FF3141E54
---

# Get-KdsConfiguration

## SYNOPSIS
Retrieves the current configuration of the Microsoft Group Key Distribution Service (KdsSvc) from Active Directory (AD).

## SYNTAX

```
Get-KdsConfiguration [<CommonParameters>]
```

## DESCRIPTION
The **Get-KdsConfiguration** cmdlet retrieves the current configuration of the Microsoft Group Key Distribution Service (KdsSvc) from Active Directory (AD).
The KDS configuration defines how keys are generated from the root keys.

## EXAMPLES

### Example 1: Retrieve the current KDS configuration
```
PS C:\>Get-KdsConfiguration
```

This example retrieves the current configuration of the Microsoft Group KdsSvc from AD.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
This cmdlet accepts no input objects.

## OUTPUTS

### Microsoft.KeyDistributionService.KdsServerConfiguration
A KdsServerConfiguration object contains information such as the key derivation function (KDF) algorithm and secret agreement algorithm used in key generation.

## NOTES

## RELATED LINKS

[Add-KdsRootKey](./Add-KdsRootKey.md)

[Clear-KdsCache](./Clear-KdsCache.md)

[Get-KdsRootKey](./Get-KdsRootKey.md)

[Set-KdsConfiguration](./Set-KdsConfiguration.md)

[Test-KdsRootKey](./Test-KdsRootKey.md)

