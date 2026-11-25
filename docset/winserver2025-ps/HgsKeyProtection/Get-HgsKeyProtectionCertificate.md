---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.KpsServer.Administration.dll-Help.xml
Module Name: HgsKeyProtection
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgskeyprotection/get-hgskeyprotectioncertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HgsKeyProtectionCertificate
---

# Get-HgsKeyProtectionCertificate

## SYNOPSIS
Gets key certificates in the Key Protection Service.

## SYNTAX

### GetMultipleCerts (Default)
```
Get-HgsKeyProtectionCertificate [-CertificateType <KeyCertificateType>] [-IsEnabled <Boolean>]
 [-IsPrimary <Boolean>] [<CommonParameters>]
```

### GetOneCert
```
Get-HgsKeyProtectionCertificate -CertificateType <KeyCertificateType> -Thumbprint <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-HgsKeyProtectionCertificate** cmdlet gets key certificates in the Key Protection Service.

## EXAMPLES

### Example 1: Get all key certificates
```
PS C:\> Get-HgsKeyProtectionCertificate
```

This command gets all key certificates from the Key Protection Service.

### Example 2: Get a specific key certificate
```
PS C:\> Get-HgsKeyProtectionCertificate -CertificateType Encryption -Thumbprint "a17dd68f4ecc499bbe65ee18718123da"
```

This command gets a key certificate that has the specified type and thumbprint.

### Example 3: Get enabled non-primary key certificates
```
PS C:\> Get-HgsKeyProtectionCertificate -IsEnabled $True -IsPrimary $False
```

This command gets all key certificates that are enabled but not primary.

## PARAMETERS

### -CertificateType
Specifies of the type of the certificate that this cmdlet gets.
The acceptable values for this parameter are:The acceptable values for this parameter are:

- Signing
- Encryption

If you do not specify this parameter, the cmdlet gets both signing and encryption certificates.

```yaml
Type: KeyCertificateType
Parameter Sets: GetMultipleCerts
Aliases:
Accepted values: Signing, Encryption

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: KeyCertificateType
Parameter Sets: GetOneCert
Aliases:
Accepted values: Signing, Encryption

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsEnabled
Specifies whether to get enabled or disabled key certificates.
Specify a value of $True to get only enabled certificates.
Specify a value of $False to get only disabled certificates.
If you do not specify this parameter, the cmdlet gets both enabled and disabled certificates.

```yaml
Type: Boolean
Parameter Sets: GetMultipleCerts
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsPrimary
Specifies whether to get the primary key certificate.
Specify a value of $True to get only the primary certificate.
Specify a value of $False to get only certificates that are not primary.
If you do not specify this parameter, the cmdlet gets both primary and not primary certificates.

```yaml
Type: Boolean
Parameter Sets: GetMultipleCerts
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Thumbprint
Specifies the thumbprint of the certificate to get.
If you specify this parameter, you must also specify the **CertificateType** parameter.

```yaml
Type: String
Parameter Sets: GetOneCert
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
You cannot pipe input to this cmdlet.

## OUTPUTS

### Microsoft.Windows.KpsServer.Common.Store.Data.KeyCertificate
This cmdlet returns a key certificate.
The object contains the following fields:

- **Thumbprint**.
The thumbprint of the certificate.
- **CertificateType**.
The type of the certificate.
Valid values are: Encryption and Signing.
- **Enabled**.
Whether the certificate is enabled.
- **Primary**.
Whether this certificate is the primary certificate.
- **Certificate**.
The full **X509Certificate2** object associated with this key certificate.

## NOTES

## RELATED LINKS

[Add-HgsKeyProtectionCertificate](./Add-HgsKeyProtectionCertificate.md)

[Remove-HgsKeyProtectionCertificate](./Remove-HgsKeyProtectionCertificate.md)

[Set-HgsKeyProtectionCertificate](./Set-HgsKeyProtectionCertificate.md)

