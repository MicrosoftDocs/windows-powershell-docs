---
external help file: Microsoft.CertificateServices.Administration.Commands.dll-Help.xml
Module Name: ADCSAdministration
online version: 
schema: 2.0.0
title: Get-CAAuthorityInformationAccess
ms.author: kenwith
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: E659A9D5-6E7F-49FE-80DE-9E91ACA2BA4A
---

# Get-CAAuthorityInformationAccess

## SYNOPSIS
Gets the Authority Information Access (AIA) and Online Certificate Status Protocol (OCSP) URI information set on the AIA extension of the certification authority (CA) properties.

## SYNTAX

```
Get-CAAuthorityInformationAccess [<CommonParameters>]
```

## DESCRIPTION
The Get-CAAuthorityInformationAccess cmdlet gets the Authority Information Access (AIA) and Online Certificate Status Protocol (OCSP) URI information set on the AIA extension of the certification authority (CA) properties.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Get-CAAuthorityInformationAccess
```

Description

-----------

Returns the current authority information access (AIA) and online certificate status protocol (OCSP) settings information for the certification authority (CA).

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None.

## OUTPUTS

### Microsoft.CertificateServices.Administration.Commands.CA.AuthorityInformationAccess
Output object is an array of Authority Information Access (AIA) (Microsoft.CertificateServices.Management.Cmdlets.CA.AuthorityInformationAcces) objects.
Each object will contain URI and different Boolean properties as follows:

Name: Type

Uri: String

AddToCertificateAia: Boolean

AddToCertificateOcsp: Boolean

## NOTES

## RELATED LINKS

[Add-CAAuthorityInformationAccess](./Add-CAAuthorityInformationAccess.md)

[Remove-CAAuthorityInformationAccess](./Remove-CAAuthorityInformationAccess.md)

