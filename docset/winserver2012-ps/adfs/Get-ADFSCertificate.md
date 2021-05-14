---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
Module Name: ADFS
online version: https://docs.microsoft.com/powershell/module/adfs/get-adfscertificate?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-ADFSCertificate

## SYNOPSIS
Gets the certificates that are in the Federation Service.

## SYNTAX

### ByType (Default)
```
Get-ADFSCertificate [[-CertificateType] <String[]>] [<CommonParameters>]
```

### ByReference
```
Get-ADFSCertificate [-Thumbprint] <String[]> [<CommonParameters>]
```

## DESCRIPTION
The Get-ADFSCertificate cmdlet retrieves the certificates that the Federation Service uses for token signing, token decrypting, card signing and securing service communications.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Get-ADFSCertificate -CertificateType "Token-Signing"
```

Description

-----------

Gets the token-signing certificates for the Federation Service.

## PARAMETERS

### -CertificateType
Specifies the type of the certificate to retrieve.
Possible certificate types include the following:

Token-Signing, Token-Encryption, Service-Communications, or Infocard-Signing.

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

### None

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.ServiceCertificate
A class structure that represents the certificate objects for the Federation Service.

## NOTES
* You can use the Get-ADFSCertificate cmdlet without any parameters to get all the certificates.

## RELATED LINKS

[Add-ADFSCertificate](./Add-ADFSCertificate.md)

[Remove-ADFSCertificate](./Remove-ADFSCertificate.md)

[Update-ADFSCertificate](./Update-ADFSCertificate.md)

