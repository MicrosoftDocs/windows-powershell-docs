---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
Module Name: ADFS
online version: https://learn.microsoft.com/powershell/module/adfs/remove-adfscertificate?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-ADFSCertificate

## SYNOPSIS
Removes a certificate from the Federation Service.

## SYNTAX

### TargetCertificate (Default)
```
Remove-ADFSCertificate [-TargetCertificate] <ServiceCertificate> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByProperties
```
Remove-ADFSCertificate -CertificateType <String> -Thumbprint <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Remove-ADFSCertificate cmdlet removes a certificate from the Federation Service.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Remove-ADFSCertificate -CertificateType Token-Signing -Thumbprint ‎fedd995b45e633d4ef30fcbc8f3a48b627e9a28b
```

Description

-----------

Removes a token-signing certificate from the Federation Service.

## PARAMETERS

### -CertificateType
Specifies the type of the certificate to remove.
Possible certificate types are

Token-Signing, Token-Encryption, Service-Communications, or Infocard-Signing.

```yaml
Type: String
Parameter Sets: ByProperties
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

### -TargetCertificate
Specifies the certificate to remove.
This value is typically taken from the pipeline.

```yaml
Type: ServiceCertificate
Parameter Sets: TargetCertificate
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Thumbprint
Specifies the thumbprint of the certificate to remove.

```yaml
Type: String
Parameter Sets: ByProperties
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.IdentityServer.PowerShell.Resources.ServiceCertificate
A class structure that represents the service certificates for the Federation Service.

## OUTPUTS

### None

## NOTES
* Removing a certificate removes it only from the Active Directory Federation Services (AD FS) 2.0 configuration data. It does not remove or delete the certificate from the local certificate store on the server computer.

## RELATED LINKS

[Add-ADFSCertificate](./Add-ADFSCertificate.md)

[Update-ADFSCertificate](./Update-ADFSCertificate.md)

