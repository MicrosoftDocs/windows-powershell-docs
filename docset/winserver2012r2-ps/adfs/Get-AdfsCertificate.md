---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
online version: 
schema: 2.0.0
title: Get-AdfsCertificate
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: BEBB9ABA-9A5D-436A-B45A-3F03A2436D35
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
The **Get-AdfsCertificate** cmdlet retrieves the certificates that  Active Directory Federation Services (AD FS) uses for token signing, token decrypting, card signing, and securing service communications.

## EXAMPLES

### Example 1: Get the token-signing certificates
```
PS C:\>Get-AdfsCertificate -CertificateType "Token-Signing"
```

This command retrieves the token-signing certificates forAD FS.

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

