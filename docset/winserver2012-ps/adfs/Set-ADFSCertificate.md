---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
Module Name: ADFS
online version: https://docs.microsoft.com/powershell/module/adfs/set-adfscertificate?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-ADFSCertificate

## SYNOPSIS
Sets the properties of an existing certificate that the Federation Service uses to sign, decrypt, or secure communications.

## SYNTAX

```
Set-ADFSCertificate -CertificateType <String> -Thumbprint <String> [-IsPrimary] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsCertificate** cmdlet sets the properties of an existing certificate that Active Directory Federation Services (AD FS) uses to sign, decrypt, or secure communications.

## EXAMPLES

### Example 1: Set a certificate
```
PS C:\>Set-AdfsCertificate -IsPrimary -CertificateType "Token-Signing" -Thumbprint ‎"fedd995b45e633d4ef30fcbc8f3a48b627e9a28b"
```

Description

-----------

Sets the primary token-signing certificate.

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
Specifies whether the certificate is primary or not.
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

[Add-ADFSCertificate](./Add-ADFSCertificate.md)

[Get-ADFSCertificate](./Get-ADFSCertificate.md)

[Remove-ADFSCertificate](./Remove-ADFSCertificate.md)

[Update-ADFSCertificate](./Update-ADFSCertificate.md)

