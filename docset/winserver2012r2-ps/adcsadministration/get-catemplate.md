---
external help file: Microsoft.CertificateServices.Administration.Commands.dll-Help.xml
Module Name: ADCSAdministration
online version: 
schema: 2.0.0
title: Get-CATemplate
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 26067498-C23B-4EAB-97D1-932508F43FCE
---

# Get-CATemplate

## SYNOPSIS
Gets the list of templates set on the certification authority (CA) for issuance of certificates.

## SYNTAX

```
Get-CATemplate [<CommonParameters>]
```

## DESCRIPTION
The Get-CATemplate cmdlet gets the list of templates set on the CA for issuance of certificates.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Get-CATemplate
```

Description

-----------

Return a list of certificate template entries that each contain a template name.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.CertificateServices.Administration.Commands.Common.CertificateTemplate
The output object type will contain an array of certificate template objects which will have two properties: (1) Object Name and (2) Object ID (OID).
Both properties are of string type.

## NOTES

## RELATED LINKS

[Add-CATemplate](./Add-CATemplate.md)

[Remove-CATemplate](./Remove-CATemplate.md)

