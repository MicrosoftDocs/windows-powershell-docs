---
author: brianlic-msft
description: 
external help file: Microsoft.CertificateServices.Administration.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-27
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-CACrlDistributionPoint
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
C:\PS>Get-CACrlDistributionPoint
```

This command gets a CA certificate revocation list (CRL) distribution point (CDP) type object, which contains the settings information and uniform resource indicator (URI) that correspond to the CDP for the current CA.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### none

## OUTPUTS

### Microsoft.CertificateServices.Administration.Commands.CA.CrlDistributionPoint
This cmdlet returns an array of **Microsoft.CertificateServices.Management.Cmdlets.CA.CrlDistributionPoint** objects.
Each object contains URI and different Boolean properties as follows:

PublishToServer: boolean

PublishDeltaToServer: boolean

AddToCertificateCdp: boolean

AddToFreshestCrl: boolean

AddToCrlCdp: boolean

AddToCrlIdp: boolean

Uri: String

## NOTES

## RELATED LINKS

[Add-CACrlDistributionPoint](./Add-CACrlDistributionPoint.md)

[Remove-CACrlDistributionPoint](./Remove-CACrlDistributionPoint.md)

