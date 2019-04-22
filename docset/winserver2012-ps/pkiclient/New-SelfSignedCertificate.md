---
external help file: Microsoft.CertificateServices.PKIClient.Cmdlets.dll-Help.xml
ms.assetid: 72FCDAEA-BB33-40C6-AFCE-E7C33CF622D0
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# New-SelfSignedCertificate

## SYNOPSIS
Creates a new self-signed certificate for testing purposes.

## SYNTAX

```
New-SelfSignedCertificate [-DnsName <String[]>] [-CloneCert <Certificate>] [-CertStoreLocation <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-SelfSignedCertificate** cmdlet creates a self-signed certificate for testing purposes.
Using the **CloneCert** parameter, a test certificate can be created based on an existing certificate with all settings copied from the original certificate except for the public key.
A new key of the same algorithm and length will be created.

If an existing certificate is not being cloned, then an SSL server certificate with the following default settings is created: 

 -- Subject: Empty 

 -- Key: RSA 2048 

 -- EKUs: Client Authentication and Server Authentication 

 -- Key Usage: Digital Signature, Key Encipherment (a0) 

 -- Validity Period: One year

Delegation may be required when using this cmdlet with Windows PowerShell® remoting and changing user configuration.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>New-SelfSignedCertificate -DnsName www.fabrikam.com, www.contoso.com -CertStoreLocation cert:\LocalMachine\My
```

This example creates a self-signed SSL server certificate in the computer MY store with the Subject Alternative Name set to www.fabrikam.com, www.contoso.com and Subject and Issuer name set to www.fabrikam.com.

### EXAMPLE 2
```
PS C:\>Set-Location -Path cert:\LocalMachine\My



PS C:\>$copyOf = (Get-ChildItem -Path E42DBC3B3F2771990A9B3E35D0C3C422779DACD7)



PS C:\>New-SelfSignedCertificate -CloneCert $copyOf
```

This example creates a copy of the certificate specified by the **CloneCert** parameter and puts it in the computer MY store.

## PARAMETERS

### -CertStoreLocation
Specifies the certificate store in which a new certificate will be stored.
The current path is the default value.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -CloneCert
Identifies the certificate to copy when creating a new certificate.
The certificate being cloned can be identified by an X509 certificate or the file path in the certificate provider.
When this parameter is used, all fields and extensions of the certificate will be inherited except the public key (a new key of the same algorithm and length will be created) and the NotAfter and NotBefore fields (the validity period for the NotBefore field is set to ten minutes in the past).

```yaml
Type: Certificate
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DnsName
Specifies one or more DNS names to put into the Subject Alternative Name extension of the certificate when a certificate to be copied is not specified via the **CloneCert** parameter.
The first DNS name is also saved as Subject Name and Issuer Name.

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

### Microsoft.CertificateServices.Commands.Certificate
The Certificate object can either be provided as a Path object to a certificate or a X509Certificate2 object.

## OUTPUTS

### System.Security.Cryptography.X509Certificates.X509Certificate2
A X509Certificate2 object for the certificate that has been created.

## NOTES

## RELATED LINKS

[Get-ChildItem](http://go.microsoft.com/fwlink/?LinkId=204557)

[Set-Location](http://go.microsoft.com/fwlink/?LinkId=113397)

