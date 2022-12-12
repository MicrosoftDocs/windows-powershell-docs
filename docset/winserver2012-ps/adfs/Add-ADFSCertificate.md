---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
Module Name: ADFS
online version: https://learn.microsoft.com/powershell/module/adfs/add-adfscertificate?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-ADFSCertificate

## SYNOPSIS
Adds a new certificate to the Federation Service for signing, decrypting, or securing communications.

## SYNTAX

```
Add-ADFSCertificate -CertificateType <String> -Thumbprint <String> [-IsPrimary] [-PassThru] [-WhatIf]
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
Specifies whether the certificate is primary or not. 
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
Passes an object to the pipeline.
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

[Remove-ADFSCertificate](./Remove-ADFSCertificate.md)

[Update-ADFSCertificate](./Update-ADFSCertificate.md)

