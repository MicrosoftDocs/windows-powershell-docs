---
description: Checks whether the local CA trusts secure hardware for identity key attestation.
external help file: Microsoft.CertificateServices.Administration.Commands.dll-Help.xml
Module Name: ADCSAdministration
online version: https://learn.microsoft.com/powershell/module/adcsadministration/confirm-caattestationidentitykeyinfo?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Confirm-CAAttestationIdentityKeyInfo
---

# Confirm-CAAttestationIdentityKeyInfo

## SYNOPSIS
Checks whether the local CA trusts secure hardware for identity key attestation.

## SYNTAX

### PublicKeyHash
```
Confirm-CAAttestationIdentityKeyInfo [-PublicKeyHash] <String> [<CommonParameters>]
```

### Certificate
```
Confirm-CAAttestationIdentityKeyInfo [-Certificate] <X509Certificate2> [<CommonParameters>]
```

## DESCRIPTION
The **Confirm-CAAttestationIdentityKeyInfo** cmdlet checks whether the local certification authority (CA) trusts secure hardware, such as a Trusted Platform Module (TPM), for identity key attestation. The Attestation Identity Key (AIK) replaces the Endorsement Key as an identity for the TPM. An Attestation Identity Key is permanently embedded in the security hardware. The public portion of the key helps to recognize genuine security hardware.

This cmdlet verifies whether the AIK public certificate connects through a certificate chain to an anchor that the CA trusts. Specify an X509 certificate by using the **Certificate** parameter.

This cmdlet checks whether the AIK public key exists as a file in a folder configured at the local CA for key attestation. Specify the public key by using the **PublicKeyHash** parameter.

## EXAMPLES

### Example 1: Check certificate
```
Confirm-CAAttestationIdentityKeyInfo -Certificate Contoso87.cer

True
```

This command checks whether the certificate `Contoso87.cer` connects, by using a certificate chain, to a trusted anchor.
This example returns a value of `$True`.

### Example 2: Check a key
```
Confirm-CAAttestationIdentityKeyInfo -PublicKeyHash "0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef"

False
```

The command checks for the public certificate specified as an SHA-256 hash code.
This example returns a value of `$False`.
The CA does not have this public key.

## PARAMETERS

### -Certificate
Specifies an X509 public key certificate issued to secure hardware.

```yaml
Type: X509Certificate2
Parameter Sets: Certificate
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PublicKeyHash
Specifies an Attestation Identity Key (AIK) public key of the secure hardware, as the result of the SHA-256 hash algorithm.
This value is a 64 character hexadecimal string.

```yaml
Type: String
Parameter Sets: PublicKeyHash
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Security.Cryptography.X509Certificates.X509Certificate2

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS

[Confirm-CAEndorsementKeyInfo](Confirm-CAEndorsementKeyInfo.md)

[Add-CAAuthorityInformationAccess](Add-CAAuthorityInformationAccess.md)

[Add-CACrlDistributionPoint](Add-CACrlDistributionPoint.md)

[Backup-CARoleService](Backup-CARoleService.md)

[Confirm-CAEndorsementKeyInfo](Confirm-CAEndorsementKeyInfo.md)
