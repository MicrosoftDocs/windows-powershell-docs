---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.PKIClient.Cmdlets.dll-Help.xml
Module Name: PKI
ms.date: 10/06/2019
online version: https://learn.microsoft.com/powershell/module/pki/new-selfsignedcertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-SelfSignedCertificate
---

# New-SelfSignedCertificate

## SYNOPSIS
Creates a new self-signed certificate for testing purposes.

## SYNTAX

```
New-SelfSignedCertificate [-SecurityDescriptor <FileSecurity>] [-TextExtension <String[]>]
 [-Extension <X509Extension[]>] [-HardwareKeyUsage <HardwareKeyUsage[]>]
 [-KeyUsageProperty <KeyUsageProperty[]>] [-KeyUsage <KeyUsage[]>]
 [-KeyProtection <KeyProtection[]>] [-KeyExportPolicy <KeyExportPolicy[]>]
 [-KeyLength <Int32>] [-KeyAlgorithm <String>] [-SmimeCapabilities] [-ExistingKey]
 [-KeyLocation <String>] [-SignerReader <String>] [-Reader <String>]
 [-SignerPin <SecureString>] [-Pin <SecureString>] [-KeyDescription <String>]
 [-KeyFriendlyName <String>] [-Container <String>] [-Provider <String>]
 [-CurveExport <CurveParametersExportType>] [-KeySpec <KeySpec>] [-Type <CertificateType>]
 [-FriendlyName <String>] [-NotAfter <DateTime>] [-NotBefore <DateTime>]
 [-SerialNumber <String>] [-Subject <String>] [-DnsName <String[]>]
 [-SuppressOid <String[]>] [-HashAlgorithm <String>] [-AlternateSignatureAlgorithm]
 [-TestRoot] [-Signer <Certificate>] [-CloneCert <Certificate>]
 [-CertStoreLocation <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `New-SelfSignedCertificate` cmdlet creates a self-signed certificate for testing purposes. Using
the **CloneCert** parameter, a test certificate can be created based on an existing certificate with
all settings copied from the original certificate except for the public key. The cmdlet creates a
new key of the same algorithm and length.

Delegation may be required when using this cmdlet with Windows PowerShell remoting and changing user
configuration.

## EXAMPLES

### EXAMPLE 1

```powershell
$params = @{
    DnsName = 'www.fabrikam.com', 'www.contoso.com'
    CertStoreLocation = 'Cert:\LocalMachine\My'
}
New-SelfSignedCertificate @params
```

This example creates a self-signed SSL server certificate in the computer `MY` store with the subject
alternative names `www.fabrikam.com` and `www.contoso.com` and the Subject and Issuer name set to
`www.fabrikam.com`.

### EXAMPLE 2

```powershell
Set-Location -Path 'Cert:\LocalMachine\My'
PS Cert:\LocalMachine\My> $OldCert = (Get-ChildItem -Path E42DBC3B3F2771990A9B3E35D0C3C422779DACD7)
PS Cert:\LocalMachine\My> New-SelfSignedCertificate -CloneCert $OldCert
```

This example creates a copy of the certificate specified by the **CloneCert** parameter and puts it
in the computer `MY` store.

### EXAMPLE 3

```powershell
$params = @{
    Type = 'Custom'
    Subject = 'E=patti.fuller@contoso.com,CN=Patti Fuller'
    TextExtension = @(
        '2.5.29.37={text}1.3.6.1.5.5.7.3.4',
        '2.5.29.17={text}email=patti.fuller@contoso.com&upn=pattifuller@contoso.com' )
    KeyAlgorithm = 'RSA'
    KeyLength = 2048
    SmimeCapabilities = $true
    CertStoreLocation = 'Cert:\CurrentUser\My'
}
New-SelfSignedCertificate @params
```

This example creates a self-signed S/MIME certificate in the user `MY` store. The certificate uses
the default provider, which is the `Microsoft Software Key Storage Provider`. The certificate uses
an `RSA` asymmetric key with a key size of `2048` bits. This certificate has the subject alternative
names of `patti.fuller@contoso.com` as RFC822 and `pattifuller@contoso.com` as Principal Name.

This command does not specify the **NotAfter** parameter. Therefore, the certificate expires in one
year.

### EXAMPLE 4

```powershell
$params = @{
    Type = 'Custom'
    Subject = 'CN=Patti Fuller,OU=UserAccounts,DC=corp,DC=contoso,DC=com'
    TextExtension = @(
        '2.5.29.37={text}1.3.6.1.5.5.7.3.2',
        '2.5.29.17={text}upn=pattifuller@contoso.com' )
    KeyUsage = 'DigitalSignature'
    KeyAlgorithm = 'RSA'
    KeyLength = 2048
    CertStoreLocation = 'Cert:\CurrentUser\My'
}
New-SelfSignedCertificate @params
```

This example creates a self-signed client authentication certificate in the user `MY` store. The
certificate uses the default provider, which is the `Microsoft Software Key Storage Provider`. The
certificate uses an `RSA` asymmetric key with a key size of `2048` bits. The certificate has a
subject alternative name of `pattifuller@contoso.com`.

The certificate expires in one year.

### EXAMPLE 5

```powershell
$params = @{
    Type = 'Custom'
    Subject = 'CN=Patti Fuller,OU=UserAccounts,DC=corp,DC=contoso,DC=com'
    TextExtension @(
        '2.5.29.37={text}1.3.6.1.5.5.7.3.2',
        '2.5.29.17={text}upn=pattifuller@contoso.com' )
    KeyUsage = 'DigitalSignature'
    KeyAlgorithm = 'ECDSA_nistP256'
    CurveExport = 'CurveName'
    CertStoreLocation = 'Cert:\CurrentUser\My'
}
New-SelfSignedCertificate @params
```

This example creates a self-signed client authentication certificate in the user `MY` store. The
certificate uses the default provider, which is the `Microsoft Software Key Storage Provider`. The
certificate uses an elliptic curve asymmetric key and the curve parameters `nist256`, which creates
a 256-bit key. The subject alternative name is `pattifuller@contoso.com`.

The certificate expires in one year.

### EXAMPLE 6

```powershell
$params = @{
    Type = 'Custom'
    Provider = 'Microsoft Platform Crypto Provider'
    Subject = 'CN=Patti Fuller'
    TextExtension = @(
        '2.5.29.37={text}1.3.6.1.5.5.7.3.2',
        '2.5.29.17={text}upn=pattifuller@contoso.com' )
    KeyExportPolicy = 'NonExportable'
    KeyUsage = 'DigitalSignature'
    KeyAlgorithm = 'RSA'
    KeyLength = 2048
    CertStoreLocation = 'Cert:\CurrentUser\My'
}
New-SelfSignedCertificate @params
```

This example creates a self-signed client authentication certificate in the user `MY` store. The
certificate uses the `Microsoft Platform Crypto Provider`. This provider uses the Trusted Platform
Module (TPM) of the device to create the asymmetric key. The certificate uses an `RSA` asymmetric
key with a key size of `2048` bits. The key is not exportable. The subject alternative name is
`pattifuller@contoso.com`. The certificate expires in one year.

### EXAMPLE 7

```powershell
$params = @{
    Type = 'Custom'
    Container = 'test*'
    Subject = 'CN=Patti Fuller'
    TextExtension = @(
        '2.5.29.37={text}1.3.6.1.5.5.7.3.2',
        '2.5.29.17={text}upn=pattifuller@contoso.com' )
    KeyUsage = 'DigitalSignature'
    KeyAlgorithm = 'RSA'
    KeyLength = 2048
    NotAfter = (Get-Date).AddMonths(6)
}
New-SelfSignedCertificate @params
```

This example creates a self-signed client authentication certificate in the user MY store. The
certificate uses the default provider, which is the `Microsoft Software Key Storage Provider`. The
certificate uses an `RSA` asymmetric key with a key size of `2048` bits. The subject alternative
name is `pattifuller@contoso.com`.

This command specifies a value for **NotAfter**. The certificate expires in six months.

### EXAMPLE 8

```powershell
$params = @{
    Type = 'Custom'
    Subject = 'E=patti.fuller@contoso.com,CN=Patti Fuller'
    TextExtension = @(
        '2.5.29.37={text}1.3.6.1.5.5.7.3.4',
        '2.5.29.17={text}email=patti.fuller@contoso.com&email=pattifuller@contoso.com' )
    KeyAlgorithm = 'RSA'
    KeyLength = 2048
    SmimeCapabilities = $true
    CertStoreLocation = 'Cert:\CurrentUser\My'
}
New-SelfSignedCertificate @params
```

This example creates a self-signed S/MIME certificate in the user `MY` store. The certificate uses
the default provider, which is the `Microsoft Software Key Storage Provider`. The certificate uses
an `RSA` asymmetric key with a key size of `2048` bits. This certificate has the subject alternative
names of `patti.fuller@contoso.com` and `pattifuller@contoso.com` both as RFC822.

This command does not specify the **NotAfter** parameter. Therefore, the certificate expires in one
year.

### EXAMPLE 9

```powershell
$params = @{
    Subject = 'localhost'
    TextExtension = @('2.5.29.17={text}DNS=localhost&IPAddress=127.0.0.1&IPAddress=::1')
}
New-SelfSignedCertificate @params
```

This example creates a self-signed SSL server certificate with Subject and Issuer name set to
`localhost` and with subject alternative name set to **IPAddress** `127.0.0.1` and `::1` via
**TextExtension**.

## PARAMETERS

### -AlternateSignatureAlgorithm

Indicates that this cmdlet uses RSA-PSS (PKCSv2.1) or an elliptic curve cryptography (ECC)
equivalent. If you do not specify this parameter, the cmdlet uses the default, RSA-PSS (PKCSv1.5) or
an ECC equivalent.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertStoreLocation

Specifies the certificate store in which to store the new certificate. If the current path is
`Cert:\CurrentUser` or `Cert:\CurrentUser\My`, the default store is `Cert:\CurrentUser\My`. If the
current path is `Cert:\LocalMachine` or `Cert:\LocalMachine\My`, the default store is
`Cert:\LocalMachine\My`. Otherwise, you must specify `Cert:\CurrentUser\My` or
`Cert:\LocalMachine\My` for this parameter. This parameter does not support other certificate
stores.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CloneCert

Identifies the certificate to copy when creating a new certificate. The certificate being cloned can
be identified by an X509 certificate or the file path in the certificate provider. When this
parameter is used, all fields and extensions of the certificate will be inherited except the
**NotAfter** and **NotBefore** fields and the public key. A new key of the same algorithm and length
will be created. The default validity period will be the same as the certificate to copy, except
that the **NotBefore** field will be set to ten minutes in the past.

```yaml
Type: Microsoft.CertificateServices.Commands.Certificate
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Container

Specifies the name of the container in which this cmdlet stores the key for the new certificate.

When you create a key, a trailing asterisk (`*`) indicates that the rest of the container name
string is a prefix. An appended GUID string makes the container name unique.

When you use an existing key, the container name must identify an existing key.
You may also have to specify the provider.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CurveExport

Specifies how the public key parameters for an elliptic curve key are represented in the new
certificate. The acceptable values for this parameter are:

- `CurveParameters`
- `CurveName`
- `None`

The default value, `None`, indicates that this cmdlet uses the default value from the underlying key
storage provider (KSP). This parameter is not supported with the RSA algorithm or with cryptographic
service providers (CSPs).

```yaml
Type: Microsoft.CertificateServices.Commands.CurveParametersExportType
Parameter Sets: (All)
Aliases:
Accepted values: None, CurveParameters, CurveName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DnsName

Specifies one or more DNS names to put into the subject alternative name extension of the
certificate when a certificate to be copied is not specified via the **CloneCert** parameter. The
first DNS name is also saved as the Subject Name. If no signing certificate is specified, the first
DNS name is also saved as the Issuer Name.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExistingKey

Indicates that this cmdlet uses an existing key. If you do not specify this parameter, this cmdlet
creates a new key. Creating a certificate from an existing key creates a new key with a new
container.

When you use an existing key, specify values for the **Container** parameter, the **Provider**
parameter, and the **CertStoreLocation** parameter. **CertStoreLocation** determines the context.
The context is user or computer.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Extension

Specifies an array of certificate extensions, as **X509Extension** objects, that this cmdlet
includes in the new certificate.

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Extension[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName

Specifies a friendly name for the new certificate.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HardwareKeyUsage

Specifies how a hardware key associated with the new certificate may be used. This parameter applies
only when you specify the `Microsoft Platform Crypto Provider`. The acceptable values for this
parameter are:

- `None`
- `SignatureKey`
- `EncryptionKey`
- `GenericKey`
- `StorageKey`
- `IdentityKey`

The default value, `None`, indicates that this cmdlet uses the default value from the underlying
KSP.

```yaml
Type: Microsoft.CertificateServices.Commands.HardwareKeyUsage[]
Parameter Sets: (All)
Aliases:
Accepted values: None, SignatureKey, EncryptionKey, GenericKey, StorageKey, IdentityKey

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HashAlgorithm

Specifies the name of the hash algorithm to use to sign the new certificate. The default hash
algorithm depends on the provider that stores the private key used to sign the new certificate.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyAlgorithm

Specifies the name of the algorithm that creates the asymmetric keys that are associated with the
new certificate. Available asymmetric key algorithms are RSA and Elliptic Curve Digital Signature
Algorithms (ECDSA).

The elliptic curve algorithm syntax is the following:

`ECDSA_{curvename}`

To obtain a value for `{curvename}`, use the `certutil -displayEccCurve` command.

Valid curve names contain a value in the **Curve OID** column in the output of the
`certutil -displayEccCurve` command.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyDescription

Specifies a description for the private key that is associated with the new certificate.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyExportPolicy

Specifies the policy that governs the export of the private key that is associated with the
certificate.

The default value of `ExportableEncrypted` is not compatible with KSP and CSPs that do not allow key
export. These include the `Microsoft Smart Card Key Storage Provider` and the
`Microsoft Platform Crypto Key Storage Provider`. Specify `NonExportable` for providers that do not
allow key export.

```yaml
Type: Microsoft.CertificateServices.Commands.KeyExportPolicy[]
Parameter Sets: (All)
Aliases:
Accepted values: NonExportable, ExportableEncrypted, Exportable

Required: False
Position: Named
Default value: ExportableEncrypted
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyFriendlyName

Specifies a friendly name for the private key that is associated with the new certificate.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyLength

Specifies the length, in bits, of the key that is associated with the new certificate.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyLocation

Specifies the file system location where this cmdlet stores the private keys associated with the new
certificate. Specify this parameter only when you specify the `Microsoft Platform Crypto Provider`.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyProtection

Specifies the level of protection required to access the private key that is associated with the
certificate. The acceptable values for this parameter are:

- `Protect`
- `ProtectHigh`
- `ProtectFingerPrint`
- `None`

The default value, `None`, indicates that this cmdlet uses the default value from the underlying KSP
or CSP. For most KSPs and CSPs, the default means that no user interface is required to create and
use the private key. A user interface is required if the provider always requires a user interface,
such as a smart card, or if the default configuration of the provider has been changed.

```yaml
Type: Microsoft.CertificateServices.Commands.KeyProtection[]
Parameter Sets: (All)
Aliases:
Accepted values: None, Protect, ProtectHigh, ProtectFingerPrint

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeySpec

Specifies whether the private key associated with the new certificate can be used for signing,
encryption, or both. The acceptable values for this parameter are:

- `KeyExchange`
- `Signature`
- `None`

The default value, `None`, indicates that this cmdlet uses the default value from the underlying
CSP.

If the private key is managed by a legacy CSP, the value is `KeyExchange` or `Signature`. If the key
is managed by a Cryptography Next Generation (CNG) KSP, the value is `None`.

```yaml
Type: Microsoft.CertificateServices.Commands.KeySpec
Parameter Sets: (All)
Aliases:
Accepted values: None, KeyExchange, Signature

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyUsage

Specifies the key usages set in the key usage extension of the certificate. The acceptable values
for this parameter are:

- `CertSign`
- `CRLSign`
- `DataEncipherment`
- `DecipherOnly`
- `DigitalSignature`
- `EncipherOnly`
- `KeyAgreement`
- `KeyEncipherment`
- `None`
- `NonRepudiation`

The value, `None`, indicates that this cmdlet does not include the **KeyUsage** extension in the new
certificate.

```yaml
Type: Microsoft.CertificateServices.Commands.KeyUsage[]
Parameter Sets: (All)
Aliases:
Accepted values: None, EncipherOnly, CRLSign, CertSign, KeyAgreement, DataEncipherment, KeyEncipherment, NonRepudiation, DigitalSignature, DecipherOnly

Required: False
Position: Named
Default value: DigitalSignature,KeyEncipherment
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyUsageProperty

Specifies the key usages for the key usages property of the private key. The acceptable values for
this parameter are:

- `All`
- `Decrypt`
- `KeyAgreement`
- `None`
- `Sign`

The default value, `None`, indicates that this cmdlet uses the default value from the underlying
KSP.

```yaml
Type: Microsoft.CertificateServices.Commands.KeyUsageProperty[]
Parameter Sets: (All)
Aliases:
Accepted values: None, Decrypt, Sign, KeyAgreement, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotAfter

Specifies the date and time, as a **DateTime** object, that the certificate expires. To obtain a
**DateTime** object, use the `Get-Date` cmdlet. The default value for this parameter is one year
after the certificate was created.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotBefore

Specifies the date and time, as a **DateTime** object, when the certificate becomes valid. The
default value for this parameter is 10 minutes before the certificate was created.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pin

Specifies the personal identification number (PIN) used to access the private key of the new
certificate.

```yaml
Type: System.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Provider

Specifies the name of the KSP or CSP that this cmdlet uses to create the certificate. See
[Cryptographic Providers](/windows/desktop/SecCertEnroll/understanding-cryptographic-providers) for
more information. Some acceptable values include:

- `Microsoft Software Key Storage Provider`
- `Microsoft Smart Card Key Storage Provider`
- `Microsoft Platform Crypto Provider`
- `Microsoft Strong Cryptographic Provider`
- `Microsoft Enhanced Cryptographic Provider v1.0`
- `Microsoft Enhanced RSA and AES Cryptographic Provider`
- `Microsoft Base Cryptographic Provider v1.0`
- The name of a third party KSP or CSP

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Reader

Specifies the name of the smart card reader on which to store the private key for the new
certificate.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecurityDescriptor

Specifies the private key security descriptor as a **FileSecurity** object. Read access is required
to use the private key. This parameter does not apply to providers that do not support security
descriptors on private keys, including the smart card CSP and smart card KSP.

```yaml
Type: System.Security.AccessControl.FileSecurity
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SerialNumber

Specifies a serial number, as a hexadecimal string, that is associated with the new certificate. If
you do not specify this parameter, this cmdlet assigns a pseudo-randomly generated 16-byte value.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Signer

Specifies a **Certificate** object with which this cmdlet signs the new certificate. This value must
be in the Personal certificate store of the user or device. This cmdlet must have read access to the
private key of the certificate.

```yaml
Type: Microsoft.CertificateServices.Commands.Certificate
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignerPin

Specifies the PIN that is required to access the private key of the certificate that is used to sign
the new certificate.

```yaml
Type: System.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignerReader

Specifies the name of the smart card reader that is used to sign the new certificate.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SmimeCapabilities

Indicates that the new certificate includes available encryption algorithms to a Secure/Multipurpose
Internet Mail Extensions (S/MIME) capabilities extension.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subject

Specifies the string that appears in the subject of the new certificate. This cmdlet prefixes `CN=`
to any value that does not contain an equal sign. For multiple subject relative distinguished names
(also known as RDNs), separate each subject relative distinguished name with a comma (`,`). If the
value of the relative distinguished name contains commas, separate each subject relative
distinguished name with a semicolon (`;`).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SuppressOid

Specifies an array of object identifier (also known as OID) strings that identify default extensions
to be removed from the new certificate.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TestRoot

Indicates that this cmdlet signs the new certificate by using a built-in test certificate. This
cmdlet adds the built-in test certificate to the intermediate certification authority (CA)
certificate store of the device.

This parameter is for test purposes only. The private key of the test root certificate is
essentially public.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TextExtension

Specifies an array of certificate extensions, as strings, which this cmdlet includes in the new
certificate. Each string must employ one of the following formats:

`{oid}={base64String}`, where `{oid}` is the object identifier of the extension and `{base64String}`
is a value that you provide. After decoding `{base64String}`, the value must be valid Abstract
Syntax Notation One (ASN.1). For more information, see
[Abstract Syntax Notation One (ASN.1): Specification of basic notation](http://www.itu.int/ITU-T/studygroups/com17/languages/X.680-0207.pdf).

`{oid}={hex}{hexadecimalString}`, where `{oid}` is the object identifier of the extension and
`{hexadecimalString}` is a value that you provide. After decoding `{hexadecimalString}`, the value
must be valid ASN.1.

`{oid}={text}{String}`, where `{oid}` is the object identifier of the extension and `{String}` is a
value that you provide. `{String}` must contain a textual representation of the extension value in a
format specific to each object ID. When `{String}` is processed, it will be encoded into an ASN.1
extension value before being placed into the new certificate as an extension.

To specify that an extension is critical, insert `{critical}` immediately following `{oid}=` in any
of the previous cases.

The object identifiers of some common extensions are as follows:

- Application Policy: `1.3.6.1.4.1.311.21.10`
- Application Policy Mappings: `1.3.6.1.4.1.311.21.11`
- Basic Constraints: `2.5.29.19`
- Certificate Policies: `2.5.29.32`
- Enhanced Key Usage: `2.5.29.37`
- Name Constraints: `2.5.29.30`
- Policy Mappings: `2.5.29.33`
- Subject Alternative Name: `2.5.29.17`

Application Policy extension example: `1.3.6.1.4.1.311.21.10={text}{token}={value}&{token}={value}...`

You can specify the following tokens in an Application Policy extension:

- **Flags**: Bitwise flags in hexadecimal notation: `0x{hexadecimalNumber}`
- **GUID**: A globally unique ID, such as this example: `f7c3ac41-b8ce-4fb4-aa58-3d1dc0e36b39`
- **Notice**: Text notice
- **OID**: Object identifier in dotted decimal notation, such as this example: `1.2.3.4.5`
- **URL**: The URL of a host, such as this example: `http://computer07.contoso.com`

To specify an Application Policy extension, specify the first object identifier, followed by zero or
more other `{token}={value}` entries. These entries are subordinate to the preceding object
identifier. Specify subsequent object identifiers, each followed by its subordinate
`{token}={value}` entries.

Application Policy Mappings extension example: `1.3.6.1.4.1.311.21.11={text}oid={oid}&oid={oid}...`

Certificate Policies extension example: `2.5.29.32={text}{token}={value}&{token}={value}...`

You can specify the following tokens in a Certificate Policies extension:

- **Flags**: Bitwise flags in hexadecimal notation: `0x{hexadecimalNumber}`
- **GUID**: A globally unique ID, such as this example: `f7c3ac41-b8ce-4fb4-aa58-3d1dc0e36b39`
- **Notice**: Text notice
- **OID**: Object identifier in dotted decimal notation, such as this example: `1.2.3.4.5`
- **URL**: The URL of a host, such as this example: `http://computer07.contoso.com`

To specify a Certificate Policies extension, follow the same syntax as an Application Policy
extension.

Enhanced Key Usage Object Identifiers extension example: `2.5.29.37={text}{oid},{oid}...`

These key usages have the following object identifiers:

- Client Authentication: `1.3.6.1.5.5.7.3.2`
- Server Authentication: `1.3.6.1.5.5.7.3.1`
- Secure Email: `1.3.6.1.5.5.7.3.4`
- Code Signing: `1.3.6.1.5.5.7.3.3`
- Timestamp Signing: `1.3.6.1.5.5.7.3.8`

Name Constraints extension example:
`2.5.29.30={text}subtree=include&{token}={value}&{token}={value}&subtree=exclude&{token}={value}...`

A Name Constraints extension can have **Subtree** values of `Include` and `Exclude` to specify
included and excluded names.

You can specify the following tokens in a Name Constraints extension:

- **DirectoryName**: A distinguished name such as: `CN=Name,DC=Domain,DC=com`
- **DNS**: A computer name in the following format: `computer.contoso.com`
- **Email**: An email address, such as this example: `admin@contoso.com`
- **IPAddress**: `{IPV4 address},{IPV4 subnet mask}` or `{IPV6 address},{IPV6 subnet mask}`
- **RegisteredID**: ID in dotted decimal notation, such as this example: `1.2.3.4.5`
- **UPN**: A user principal name in the following format: `admin@contoso.com`
- **URL**: The URL of a host, such as this example: `http://computer07.contoso.com/index.html`

Policy Mapping extension example: `2.5.29.33={text}oid={oid}&oid={oid}...`

Subject Alternative Name extension example: `2.5.29.17={text}token=value&token=value...`

You can specify the following tokens in a Subject Alternative Name extension:

- **DirectoryName**: A distinguished name such as: `CN=Name,DC=Domain,DC=com`
- **DNS**: A computer name in the following format: `computer.contoso.com`
- **Email**: An email address, such as this example: `admin@contoso.com`
- **GUID**: A globally unique ID, such as this example: `f7c3ac41-b8ce-4fb4-aa58-3d1dc0e36b39`
- **IPAddress**: `{IPV4 address},{IPV4 subnet mask}` or `{IPV6 address},{IPV6 subnet mask}`
- **RegisteredID**: ID in dotted decimal notation, such as this example: `1.2.3.4.5`
- **UPN**: A user principal name in the following format: `admin@contoso.com`
- **URL**: The URL of a host, such as this example: `http://computer07.contoso.com/index.html`

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type

Specifies the type of certificate that this cmdlet creates.

```yaml
Type: Microsoft.CertificateServices.Commands.CertificateType
Parameter Sets: (All)
Aliases:
Accepted values: Custom, CodeSigningCert, DocumentEncryptionCert, SSLServerAuthentication, DocumentEncryptionCertLegacyCsp

Required: False
Position: Named
Default value: SSLServerAuthentication
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.CertificateServices.Commands.Certificate

The **Certificate** object can either be provided as a Path object to a certificate or an
**X509Certificate2** object.

## OUTPUTS

### System.Security.Cryptography.X509Certificates.X509Certificate2

An **X509Certificate2** object for the certificate that has been created.

## NOTES

## RELATED LINKS

[System Store Locations](/windows/desktop/seccrypto/system-store-locations)
