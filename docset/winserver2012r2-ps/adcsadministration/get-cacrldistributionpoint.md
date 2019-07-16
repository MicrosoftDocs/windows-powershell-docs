---
external help file: Microsoft.CertificateServices.Administration.Commands.dll-Help.xml
Module Name: ADCSAdministration
online version: 
schema: 2.0.0
title: Get-CACrlDistributionPoint
ms.author: v-anbarr
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 64E481BE-BDD5-4E27-95AD-5DC930E55453
---

# Get-CACrlDistributionPoint

## SYNOPSIS
Gets all the locations set on the CRL distribution point (CDP) extension of the certification authority (CA) properties.

## SYNTAX

```
Get-CACrlDistributionPoint [<CommonParameters>]
```

## DESCRIPTION
The Get-CACRLDistributionPoint cmdlet gets all the locations set on the CRL distribution point (CDP) extension of the certification authority (CA) properties.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Get-CACrlDistributionPoint
```

Description

-----------

Returns a certification authority (CA) certificate revocation list (CRL) distribution point (CDP) type object, which contains the settings information and uniform resource indicator (URI) that correspond to the CDP for the current CA.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### none

## OUTPUTS

### Microsoft.CertificateServices.Administration.Commands.CA.CrlDistributionPoint
Output object is an array of CRL Distribution Point (CDP) (Microsoft.CertificateServices.Management.Cmdlets.CA.CrlDistributionPoint) Each object will contain URI and different Boolean properties as follows:

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

