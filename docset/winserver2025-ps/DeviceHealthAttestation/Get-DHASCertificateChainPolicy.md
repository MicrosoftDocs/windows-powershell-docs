---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.DeviceHealthAttestation.PowerShell.dll-Help.xml
Module Name: DeviceHealthAttestation
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/devicehealthattestation/get-dhascertificatechainpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DHASCertificateChainPolicy
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
PS C:\> Get-DHASCertificateChainPolicy
```

This command gets the current certificate chain policy for the Device Health Attestation service.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### CertificateChainPolicy
The **CertificateChainPolicy** object that this cmdlet returns has the following members:

- RevocationFlag.
A .NET [X509RevocationFlag enumeration](https://go.microsoft.com/fwlink/?LinkId=821152).
- RevocationMode.
A .NET [X509RevocationMode enumeration](https://go.microsoft.com/fwlink/?LinkId=821153).
- VerificationFlags.
A .NET [X509VerificationFlags enumeration](https://go.microsoft.com/fwlink/?LinkId=821154).
- UrlRetrievalTimeout.
A .NET [TimeSpan structure](https://go.microsoft.com/fwlink/?LinkId=821155).

## NOTES

## RELATED LINKS

[Set-DHASCertificateChainPolicy](./Set-DHASCertificateChainPolicy.md)

