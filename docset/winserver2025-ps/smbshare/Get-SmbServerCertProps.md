---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbServerCertProps.cdxml-help.xml
Module Name: SmbShare
ms.date: 02/22/2024
online version: https://learn.microsoft.com/powershell/module/smbshare/get-smbservercertprops?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SmbServerCertProps
---

# Get-SmbServerCertProps

## SYNOPSIS
Retrieves an SMB over QUIC-mapped certificate's properties and tests certificate validity.

## SYNTAX

```
Get-SmbServerCertProps -Name <String> -Force <CommonParameters>
```

## DESCRIPTION

The `Get-SmbServerCertProps` cmdlet retrieves the properties of a certificate associated with the
SMB server for SMB over QUIC. For more information, see [SMB over QUIC](https://aka.ms/smboverquic).

## EXAMPLES

### Example 1 - Retrieve the properties of a certificate associated with the SMB server

This command retrieves the properties and validity of the `2025-srv-01.corp.contoso.com` SMB over
QUIC endpoint certificate mapping.

```powershell
Get-SmbServerCertProps -Name 2025-srv-01.corp.contoso.com
```

```output
Checking Mapping '2025-srv-01.corp.contoso.com'.....
SMBServerCertificateMappingName : 2025-srv-01.corp.contoso.com
SelfSigned                      : True
SubjectName                     : System.Security.Cryptography.X509Certificates.X500DistinguishedName
Subject                         : CN=2025-srv-01
SubjectOid                      : System.Security.Cryptography.Oid
SubjectRawData                  : {48, 21, 49, 19...}
FriendlyName                    :
SignatureAlgorithm              : 1.2.840.113549.1.1.11 sha256RSA
Thumbprint                      : 88032B3551FAF7DE26EFFFF814AA086E3DBD2A4F
NotBefore                       : 8/20/2021 3:02:16 PM
NotAfter                        : 8/20/2022 3:02:16 PM
SendAsTrustedIssuer             : False
PublicKey                       : System.Security.Cryptography.X509Certificates.PublicKey
DnsNameList                     : {2025-srv-01.corp.contoso.com, fs1.contoso.com}

Test-Certificate result : PASS

RenewalChain:

Testing certificates in the RenewalChain.....
```

## PARAMETERS

### -Force

Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Specifies a fully-qualified DNS name or NetBIOS name that must match the certificate's subject name
or an entry in the certificate's subject alternative names.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS
