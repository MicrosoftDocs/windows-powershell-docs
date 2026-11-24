---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.RemoteAttestation.Server.PowerShell.dll-Help.xml
Module Name: HgsAttestation
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgsattestation/get-hgsattestationsignercertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HgsAttestationSignerCertificate
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Security.Cryptography.X509Certificates.X509Certificate2
This cmdlet returns an X.509 certificate.

## NOTES

## RELATED LINKS

