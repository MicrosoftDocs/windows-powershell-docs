---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.KpsServer.Administration.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: HgsKeyProtection
ms.assetid: A3DCAD26-A475-4E46-9163-2E8D3084E182
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Add-HgsKeyProtectionAttestationSignerCertificate
ms.reviewer:
---

# Add-HgsKeyProtectionAttestationSignerCertificate

## SYNOPSIS
Adds an attestation signer certificate for the trusted certificates for the Key Protection Service.

## SYNTAX

```
Add-HgsKeyProtectionAttestationSignerCertificate -Certificate <X509Certificate2> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-HgsKeyProtectionAttestationSignerCertificate** cmdlet adds the signer certificate of an attestation server to the list of certificates that the Key Protection Service trusts.
The Key Protection Service uses attestation signer certificates to verify the signatures of health certificates.
To modify the policy for an attestation signer certificate, use the **Set-HgsKeyProtectionAttestationSignerCertificatePolicy** cmdlet.

## EXAMPLES

### Example 1: Add a certificate
```
PS C:\> Add-HgsKeyProtectionAttestationSignerCertificate -Certificate $Certificate
```

This command adds the certificate stored in the **$Certificate** variable to the trusted attestation signer certificates.

## PARAMETERS

### -Certificate
Specifies an **X509Certificate2** certificate.
This cmdlet adds the certificate that this parameter specifies to the attestation signer certificates that the Key Protection Service trusts.
Specify a variable that stores an **X509Certificate2** object or an expression that gets the certificate.

```yaml
Type: X509Certificate2
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
You cannot pipe input to this cmdlet.

## OUTPUTS

### None
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-HgsKeyProtectionAttestationSignerCertificate](./Get-HgsKeyProtectionAttestationSignerCertificate.md)

[Remove-HgsKeyProtectionAttestationSignerCertificate](./Remove-HgsKeyProtectionAttestationSignerCertificate.md)

[Set-HgsKeyProtectionAttestationSignerCertificatePolicy](./Set-HgsKeyProtectionAttestationSignerCertificatePolicy.md)

