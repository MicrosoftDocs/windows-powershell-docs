---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.PKIClient.Cmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Test-Certificate
ms.reviewer:
ms.assetid: D0E2D004-0EA9-45E4-B520-F14FCA21516D
---

# Test-Certificate

## SYNOPSIS
Verifies a certificate according to the input parameters.

## SYNTAX

```
Test-Certificate [-Policy <TestCertificatePolicy>] [-User] [-EKU <String[]>] [-DNSName <String>]
 [-AllowUntrustedRoot] [-Cert] <Certificate> [<CommonParameters>]
```

## DESCRIPTION
The **Test-Certificate** cmdlet verifies a certificate according to input parameters.
The revocation status of the certificate is verified by default.
If the **AllowUntrustedRoot** parameter is specified, then a certificate chain is built but an untrusted root is allowed.
Other errors are still verified against in this case, such as expired.
If the **DNSName** parameter is used, then the DNS subject alternative name is used to verify SSL policy.
If the **EKU** parameter is used, then the specified application policy object identifiers are used to verify the chain.
If the **User** parameter is used, then the specified user context is used is to build and verify the chain.

Delegation may be required when using this cmdlet with Windows PowerShell® remoting and changing user configuration.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-ChildItem -Path Cert:\localMachine\My | Test-Certificate -Policy SSL -DNSName "dns=contoso.com"
```

This example verifies each certificate in the MY store of the local machine and verifies that it is valid for SSL with the DNS name specified.

### EXAMPLE 2
```
PS C:\>Test-Certificate -Cert cert:\currentuser\my\191c46f680f08a9e6ef3f6783140f60a979c7d3b -AllowUntrustedRoot -EKU "1.3.6.1.5.5.7.3.1" -User
```

This example verifies that the provided EKU is valid for the specified certificate and its chain.
Revocation checking is not performed.

## PARAMETERS

### -AllowUntrustedRoot
Specifies whether the root certificate is required to be trusted in chain building.
When this parameter is used, the certificate chain is built but an untrusted root is allowed.
Other errors are still verified against in this case, such as expired.
If this parameter is not specified, then revocation status is checked by default.

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

### -Cert
Specifies the certificate to test.
Either the certificate object or a path to the certificate in a certificate store can be specified.

```yaml
Type: Certificate
Parameter Sets: (All)
Aliases: PsPath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DNSName
Specifies the DNS name to verify as valid for the certificate. 
 
If this parameter is specified but not the **Policy** parameter, then the CERT_CHAIN_POLICY_SSL policy is applied and the DNS name is validated for the certificate.
If a CERT_CHAIN_POLICY_SSL policy does not exist, then the cmdlet will fail. 

If this parameter is not used and the **Policy** parameter is not specified, the default CERT_CHAIN_POLICY_BASE policy is applied.

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

### -EKU
Specifies a list of enhanced key usage (EKU) object identifiers to verify for the certificate chain.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Policy
Specifies the policies that will be applied to verify the certificate.
The acceptable values for this parameter are: AUTHENTICODE, BASE, NTAUTH, and SSL.
If this parameter is not specified, then the BASE policy is used.

```yaml
Type: TestCertificatePolicy
Parameter Sets: (All)
Aliases: 
Accepted values: BASE, SSL, AUTHENTICODE, NTAUTH

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -User
Specifies whether the user or machine context is used to test the certificate.
If this parameter is not specified, then the machine context is used.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.CertificateServices.Commands.Certificate
The **Certificate** object can either be provided as a Path object to a certificate or an **X509Certificate2** object.

## OUTPUTS

### System.Boolean
If the verification succeeds, then the return value is True; otherwise the return value is False.

## NOTES

## RELATED LINKS

[Get-ChildItem](http://go.microsoft.com/fwlink/p/?LinkId=290488)

