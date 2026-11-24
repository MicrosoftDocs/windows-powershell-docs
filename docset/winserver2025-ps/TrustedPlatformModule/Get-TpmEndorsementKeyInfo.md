---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Tpm.Commands.dll-Help.xml
Module Name: TrustedPlatformModule
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/trustedplatformmodule/get-tpmendorsementkeyinfo?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TpmEndorsementKeyInfo
---

# Get-TpmEndorsementKeyInfo

## SYNOPSIS
Gets information about the endorsement key and certificates of the TPM.

## SYNTAX

```
Get-TpmEndorsementKeyInfo [[-HashAlgorithm] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-TpmEndorsementKeyInfo** cmdlet gets information about the endorsement public key and certificates of the Trusted Platform Module (TPM).

## EXAMPLES

### Example 1: Get endorsement key information
```
PS C:\> Get-TpmEndorsementKeyInfo -Hash "Sha256"
IsPresent                : True
PublicKey                : System.Security.Cryptography.AsnEncodedData
PublicKeyHash            : 70769c52b6e24ef683693c2a0208da68d77e94192e1f4080ae7c9b97c6caa681
ManufacturerCertificates : {[Subject]
OID.2.23.133.2.3=1.2,
OID.2.23.133.2.2=C4T8SOX3.5,
OID.2.23.133.2.1=id:782F345A

[Issuer]
CN=Contoso TPM CA1, OU=Contoso
Certification Authority, O=Contoso, C=KR

[Serial Number]
77A120A

[Not Before]
6/4/2012 6:35:58 PM

[Not After]
6/4/2022 6:35:57 PM

[Thumbprint]
77378D1480AB48FEA2D4E610B2C7EEF648FEA2
}
AdditionalCertificates   : {}
```

This command gets information about the endorsement key of the TPM.
The command uses the Sha256 algorithm to hash the public key.

## PARAMETERS

### -HashAlgorithm
Specifies the hash algorithm used for the public key.
The acceptable values for this parameter are: Sha256.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: sha256

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String
This accepts the name of the algorithm, as a string, used to hash the public key.
Sha256 is the only supported algorithm.

## OUTPUTS

### EndorsementKeyObject
This cmdlet generates an **EndorsementKeyObject** object that contains the following members:

- **IsPresent**. A Boolean that represents whether the endorsement public key is known to the operating system.
- **PublicKey**. An **AsnEncodedData** object that contains the asn.1 encoded public portion of the endorsement key.
- **PublicKeyHash**. The hash, as a String, of the public key if the cmdlet used a hash algorithm.
- **ManufacturerCertificates**. A **X509Certificate2Collection** object that contains the manufacturer endorsement key certificates. This object can contain the manufacturer and platform certificates.
- **AdditionalCertificates**. A **X509Certificate2Collection** object that contains a collection of additional endorsement key certificates that are registered to the operating system, such as any enterprise certificates.

## NOTES

## RELATED LINKS

[Trusted Platform Module Cmdlets in Windows PowerShell](./trustedplatformmodule.md)

