---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.KpsServer.Administration.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: HgsKeyProtection
ms.assetid: CC46ED76-4121-49F3-A700-4588F53731EA
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-HgsKeyProtectionAttestationSignerCertificate
ms.reviewer:
---

# Get-HgsKeyProtectionAttestationSignerCertificate

## SYNOPSIS
Gets the attestation signer certificates that the Key Protection Service trusts.

## SYNTAX

```
Get-HgsKeyProtectionAttestationSignerCertificate [-Thumbprint <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-HgsKeyProtectionAttestationSignerCertificate** cmdlet gets the attestation signer certificates that the Key Protection Service trusts

## EXAMPLES

### Example 1: Get all attestation certificates
```
PS C:\> Get-HgsKeyProtectionAttestationSignerCertificate
```

This command gets all the attestation certificates signers that the Key Protection Service trusts.

### Example 2: Get a single attestation certificate
```
PS C:\> Get-HgsKeyProtectionAttestationSignerCertificate -Thumbprint "d39203a3b3544743ad552afe0615dc1f"
```

This command gets a single attestation certificate signer that the Key Protection Service trusts.
The command looks up the certificate signer by using a thumbprint.

## PARAMETERS

### -Thumbprint
Specifies the thumbprint of the attestation signer certificate to get.
If you do not specify a value for this parameter, this cmdlet gets all the attestation signer certificates for trusted attestation servers.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
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

### Microsoft.Windows.KpsServer.Common.Store.Data.AttestationCertificate
This cmdlet returns an **AttestationCertificate** object that represents an attestation signer certificate.
The object contains the following fields: 

- Certificate.
The **X509Certificate2** object. 
- AttestationCertificatePolicy.
The policy that describes further limitations on which health certificates signed by this signer certificate are trusted by the Key Protection Service.

## NOTES

## RELATED LINKS

[Add-HgsKeyProtectionAttestationSignerCertificate](./Add-HgsKeyProtectionAttestationSignerCertificate.md)

[Remove-HgsKeyProtectionAttestationSignerCertificate](./Remove-HgsKeyProtectionAttestationSignerCertificate.md)

