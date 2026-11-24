---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/remove-adfscertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-AdfsCertificate
---

# Remove-AdfsCertificate

## SYNOPSIS
Removes a certificate from AD FS.

## SYNTAX

### TargetCertificate (Default)
```
Remove-AdfsCertificate [-TargetCertificate] <ServiceCertificate> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByProperties
```
Remove-AdfsCertificate -CertificateType <String> -Thumbprint <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AdfsCertificate** cmdlet removes a certificate from Active Directory Federation Services (AD FS).

## EXAMPLES

### Example 1: Remove a token-signing certificate
```
PS C:\> Remove-AdfsCertificate -CertificateType "Token-Signing" -Thumbprint ‎"fedd995b45e633d4ef30fcbc8f3a48b627e9a28b"
```

This command removes a token-signing certificate from AD FS.

## PARAMETERS

### -CertificateType
Specifies the type of the certificate to remove.
The acceptable values for this parameter are:

- Infocard-Signing
- Service-Communications
- Token-Encryption
- Token-Signing

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.IdentityServer.PowerShell.Resources.ServiceCertificate

A ServiceCertificate object is received by the *TargetCertificate* parameter.

### System.String

A string object is received by the *Thumbprint* parameter.

## OUTPUTS

### None

## NOTES
* Removing a certificate removes it only from the AD FS configuration data. It does not remove or delete the certificate from the local certificate store on the server computer.

## RELATED LINKS

[Add-AdfsCertificate](./Add-AdfsCertificate.md)

[Get-AdfsCertificate](./Get-AdfsCertificate.md)

[Set-AdfsCertificate](./Set-AdfsCertificate.md)

[Update-AdfsCertificate](./Update-AdfsCertificate.md)

