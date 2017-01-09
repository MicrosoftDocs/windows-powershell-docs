---
author: brianlic
description: 
external help file: Microsoft.Windows.DeviceHealthAttestation.PowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-DHASCertificateChainPolicy
ms.assetid: DEECBFFC-FFD2-428A-9706-58A06659DDE3
---

# Get-DHASCertificateChainPolicy

## SYNOPSIS
Gets the certificate chain policy.

## SYNTAX

```
Get-DHASCertificateChainPolicy [<CommonParameters>]
```

## DESCRIPTION
The **Get-DHASCertificateChainPolicy** cmdlet gets the certificate chain policy enforced by the Device Health Attestation service.
The certificate chain policy specifies parameters for certificate chain verification and revocation behavior.

You must have administrator rights to run this cmdlet.

## EXAMPLES

### Example 1: Get the certificate chain policy
```
PS C:\>Get-DHASCertificateChainPolicy
```

This command gets the current certificate chain policy for the Device Health Attestation service.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### CertificateChainPolicy
The **CertificateChainPolicy** object that this cmdlet returns has the following members: 

- RevocationFlag.
A .NET X509RevocationFlag enumerationhttp://go.microsoft.com/fwlink/?LinkId=821152.
- RevocationMode.
A .NET X509RevocationMode enumerationhttp://go.microsoft.com/fwlink/?LinkId=821153.
- VerificationFlags.
A .NET X509VerificationFlags enumerationhttp://go.microsoft.com/fwlink/?LinkId=821154.
- UrlRetrievalTimeout.
A .NET TimeSpan structurehttp://go.microsoft.com/fwlink/?LinkId=821155

## NOTES

## RELATED LINKS

[Set-DHASCertificateChainPolicy](./Set-DHASCertificateChainPolicy.md)

