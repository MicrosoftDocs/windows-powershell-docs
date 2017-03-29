---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: brianlic
author: brianlic-msft
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.RemoteAttestation.Server.PowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-HgsAttestationSignerCertificate
ms.assetid: 7DB9E62C-90CD-4F74-B1DC-2BE93BEDE009
---

# Get-HgsAttestationSignerCertificate

## SYNOPSIS
Gets the public certificates for a key pair that attestation uses to sign attestation certificates.

## SYNTAX

```
Get-HgsAttestationSignerCertificate [<CommonParameters>]
```

## DESCRIPTION
The **Get-HgsAttestationSignerCertificate** cmdlet gets the signer certificate for Host Guardian Service (HGS) attestation.
The Attestation Service signs attestation certificates by using a key pair.
This cmdlet gets the public certificate that corresponds to that key pair.

## EXAMPLES

### Example 1: Get signer certificates
```
PS C:\> Get-HgsAttestationSignerCertificate
```

This command gets Attestation Service signer certificates.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Security.Cryptography.X509Certificates.X509Certificate2
This cmdlet returns an X.509 certificate.

## NOTES

## RELATED LINKS

