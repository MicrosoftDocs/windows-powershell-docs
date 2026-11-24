---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/update-adfscertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-AdfsCertificate
---

# Update-AdfsCertificate

## SYNOPSIS
Updates the certificates of AD FS.

## SYNTAX

```
Update-AdfsCertificate [[-CertificateType] <String>] [-Urgent] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Update-AdfsCertificate** cmdlet creates new certificates for Active Directory Federation Services (AD FS).
When automatic certificate rollover is enabled and AD FS is managing the certificates that are used for signing, this update cmdlet can be used to initiate a rollover.

## EXAMPLES

### Example 1: Update a token-signing certificate
```
PS C:\> Update-AdfsCertificate -CertificateType "Token-Signing"
```

This command updates the token-signing certificate.

## PARAMETERS

### -CertificateType
Specifies the type of certificate to rollover.
The acceptable values for this parameter are:

- Token-Decrypting
- Token-Signing

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Token-Decrypting, Token-Signing

Required: False
Position: 0
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

### -Urgent
Indicates that the certificate rollover should happen immediately.
An urgent rollover removes older certificates immediately.
It might result in a service outage as trusts update to use the new certificates.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.ServiceCertificate

Returns the updated ServiceCertificate object when the *PassThru* parameter is specified. By default, this cmdlet does not generate any output.

## NOTES
* The *Urgent* parameter option is useful for emergency rollover situations in which a key might be compromised.

## RELATED LINKS

[Add-AdfsCertificate](./Add-AdfsCertificate.md)

[Get-AdfsCertificate](./Get-AdfsCertificate.md)

[Remove-AdfsCertificate](./Remove-AdfsCertificate.md)

[Set-AdfsCertificate](./Set-AdfsCertificate.md)

