---
author: Kateyanne
description: 
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
manager: jasgro
Module Name: ADFS
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/adfs/add-adfscertificate?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-AdfsCertificate
---

# Add-AdfsCertificate

## SYNOPSIS
Adds a new certificate to  AD FS for signing, decrypting, or securing communications.

## SYNTAX

```
Add-AdfsCertificate -CertificateType <String> -Thumbprint <String> [-IsPrimary] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AdfsCertificate** cmdlet adds a new certificate to  Active Directory Federation Services (AD FS) for token signing, token decrypting, card signing, or securing communications.

## EXAMPLES

### Example 1: Add a token-signing certificate
```powershell
PS C:\> Add-AdfsCertificate -CertificateType "Token-Signing" -Thumbprint ‎"fedd995b45e633d4ef30fcbc8f3a48b627e9a28b"
```

This command adds a token-signing certificate with the thumbprint `fedd995b45e633d4ef30fcbc8f3a48b627e9a28b`.

## PARAMETERS

### -CertificateType
Specifies the type and purpose of the certificate.
The acceptable values for this parameter are:

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Token-Decrypting, Token-Signing

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
Indicates that the certificate is primary or not.
Primary token-signing certificates are used to digitally sign outgoing claims.
Primary token-encrypting certificates are published in federation metadata for use by trusted claims providers.
Service communications certificates are always primary certificates.

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
This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES
* Active Directory Federation Services (AD FS) 2.0 uses certificates for issuing and receiving tokens, publishing federation metadata and communicating through Secure Sockets Layer (SSL).

## RELATED LINKS

[Get-AdfsCertificate](./Get-AdfsCertificate.md)

[Remove-AdfsCertificate](./Remove-AdfsCertificate.md)

[Set-AdfsCertificate](./Set-AdfsCertificate.md)

[Update-AdfsCertificate](./Update-AdfsCertificate.md)

