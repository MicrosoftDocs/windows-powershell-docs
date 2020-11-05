---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
online version: 
schema: 2.0.0
title: Set-AdfsCertificate
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
ms.assetid: D9E57A68-5525-4728-85EE-823355901670
---

# Set-AdfsCertificate

## SYNOPSIS
Sets the properties of an existing certificate that AD FS uses to sign, decrypt, or secure communications.

## SYNTAX

```
Set-AdfsCertificate -CertificateType <String> -Thumbprint <String> [-IsPrimary] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsCertificate** cmdlet sets the properties of an existing certificate that  Active Directory Federation Services (AD FS) uses to sign, decrypt, or secure communications.

## EXAMPLES

### Example 1: Set a certificate
```
PS C:\>Set-AdfsCertificate -IsPrimary -CertificateType "Token-Signing" -Thumbprint ‎"fedd995b45e633d4ef30fcbc8f3a48b627e9a28b"
```

This command sets the primary token-signing certificate.

## PARAMETERS

### -CertificateType
Specifies the certificate type (that is, how the Federation Service uses the certificate).
The acceptable values for this parameter are:

- Service-Communications
- Token-Decrypting
- Token-Signing
```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Service-Communications, Token-Decrypting, Token-Signing

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsPrimary
Indicates that the certificate is primary.
Primary token-signing certificates are used to digitally sign outgoing claims.
Primary token-encrypting certificates are published in federation metadata for use by trusted claims providers.
Information Card signing and service communications certificates are always primary.

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

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -Thumbprint
Specifies the thumbprint of the certificate to use.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.IdentityServer.PowerShell.Resources.ServiceCertificate
A class structure that represents a service certificate.

## OUTPUTS

### None

## NOTES
* Use the **Set-AdfsRelyingPartyTrust** or **Set-AdfsClaimsProviderTrust** cmdlets, as appropriate, to modify the certificates that are associated with a relying party or a claims provider.

## RELATED LINKS

[Add-AdfsCertificate](./Add-AdfsCertificate.md)

[Get-AdfsCertificate](./Get-AdfsCertificate.md)

[Remove-AdfsCertificate](./Remove-AdfsCertificate.md)

[Update-AdfsCertificate](./Update-AdfsCertificate.md)

