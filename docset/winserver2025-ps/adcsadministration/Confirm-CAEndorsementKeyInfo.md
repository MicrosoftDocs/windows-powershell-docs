---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.Administration.Commands.dll-Help.xml
Module Name: ADCSAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/adcsadministration/confirm-caendorsementkeyinfo?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Confirm-CAEndorsementKeyInfo
---

# Confirm-CAEndorsementKeyInfo

## SYNOPSIS
Checks whether the local CA trusts secure hardware for key attestation.

## SYNTAX

### PublicKeyHash
```
Confirm-CAEndorsementKeyInfo [-PublicKeyHash] <String> [<CommonParameters>]
```

### Certificate
```
Confirm-CAEndorsementKeyInfo [-Certificate] <X509Certificate2> [<CommonParameters>]
```

## DESCRIPTION
The **Confirm-CAEndorsementKeyInfo** cmdlet checks whether the local certification authority (CA) trusts secure hardware, such as a Trusted Platform Module (TPM), for key attestation.
The cmdlet checks the endorsement key or certificate.
An endorsement key is permanently embedded in the security hardware.
The public portion of the endorsement key helps to recognize genuine security hardware.

This cmdlet verifies whether the endorsement public certificate connects by means of a certificate chain to an anchor that the CA trusts for key attestation.
Specify an X509 certificate by using the *Certificate* parameter.

This cmdlet checks whether the endorsement public key exists as a file in a folder configured at the local CA for key attestation.
Specify the public key by using the *PublicKeyHash* parameter.

## EXAMPLES

### Example 1: Check an endorsement certificate
```
PS C:\> Confirm-CAEndorsementKeyInfo -Certificate Contoso87.cer

True
```

This command checks whether the endorsement certificate Contoso87.cer connects, by means of a certificate chain, to a trusted anchor.
This example returns a value of $True.

### Example 2: Check an endorsement key
```
PS C:\> Confirm-CAEndorsementKeyInfo -PublicKeyHash "1dd117facfbdcbd8713b9c588eef305e61ce3d8e3c6e21e6323a877476ecd167"
False
```

The command checks for the endorsement public certificate specified as an SHA-256 hash code.
This example returns a value of $False.
Therefore, the CA does not have this public key.

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
Specifies an endorsement public key of the secure hardware, as the result of the SHA-256 hash algorithm.
This is a 64 character hexadecimal string.

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

