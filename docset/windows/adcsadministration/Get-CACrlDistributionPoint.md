---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.Administration.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/27/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-CACrlDistributionPoint
ms.reviewer:
ms.assetid: 64E481BE-BDD5-4E27-95AD-5DC930E55453
---

# Get-CACrlDistributionPoint

## SYNOPSIS
Gets all the locations set on the CDP extension of the CA properties.

## SYNTAX

```
Get-CACrlDistributionPoint [<CommonParameters>]
```

## DESCRIPTION
The **Get-CACRLDistributionPoint** cmdlet gets all the locations set on the CRL distribution point (CDP) extension of the certification authority (CA) properties.

## EXAMPLES

### Example 1: Get a CA certificate revocation list distribution point object
```
PS C:\> Get-CACrlDistributionPoint
```

This command gets a CA certificate revocation list (CRL) distribution point (CDP) type object, which contains the settings information and uniform resource indicator (URI) that correspond to the CDP for the current CA.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### none

## OUTPUTS

### Microsoft.CertificateServices.Administration.Commands.CA.CrlDistributionPoint
This cmdlet returns an array of **Microsoft.CertificateServices.Management.Cmdlets.CA.CrlDistributionPoint** objects.
Each object contains URI and different Boolean properties as follows:

Name | Type
-----|------
PublishToServer | Boolean
PublishDeltaToServer | Boolean
AddToCertificateCdp | Boolean
AddToFreshestCrl | Boolean
AddToCrlCdp | Boolean
AddToCrlIdp | Boolean
Uri | String

## NOTES

## RELATED LINKS

[Add-CACrlDistributionPoint](./Add-CACrlDistributionPoint.md)

[Remove-CACrlDistributionPoint](./Remove-CACrlDistributionPoint.md)

