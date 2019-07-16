---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: ADFS
ms.assetid: BEBB9ABA-9A5D-436A-B45A-3F03A2436D35
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-AdfsCertificate
ms.reviewer:
---

# Get-AdfsCertificate

## SYNOPSIS
Retrieves the certificates from AD FS.

## SYNTAX

### ByType (Default)
```
Get-AdfsCertificate [[-CertificateType] <String[]>] [<CommonParameters>]
```

### ByReference
```
Get-AdfsCertificate [-Thumbprint] <String[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsCertificate** cmdlet retrieves the certificates that Active Directory Federation Services (AD FS) uses for token signing, token decrypting, card signing, and securing service communications.

## EXAMPLES

### Example 1: Get the token-signing certificates
```
PS C:\> Get-AdfsCertificate -CertificateType "Token-Signing"
```

This command retrieves the token-signing certificates for AD FS.

## PARAMETERS

### -CertificateType
Specifies the type of the certificate to retrieve.
The acceptable values for this parameter are:

- Infocard-Signing 
- Service-Communications
- Token-Encryption
- Token-Signing

```yaml
Type: String[]
Parameter Sets: ByType
Aliases: 
Accepted values: Service-Communications, Token-Decrypting, Token-Signing

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Thumbprint
Specifies the thumbprint of the certificate to retrieve.

```yaml
Type: String[]
Parameter Sets: ByReference
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.ServiceCertificate
This cmdlet generates a class structure that represents the certificate objects for ADFS.

## NOTES
* You can use the **Get-AdfsCertificate** cmdlet without any parameters to get all the certificates.

## RELATED LINKS

[Add-AdfsCertificate](./Add-AdfsCertificate.md)

[Remove-AdfsCertificate](./Remove-AdfsCertificate.md)

[Set-AdfsCertificate](./Set-AdfsCertificate.md)

[Update-AdfsCertificate](./Update-AdfsCertificate.md)

