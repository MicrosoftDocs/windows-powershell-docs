---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.KpsServer.Administration.dll-Help.xml
Module Name: HgsKeyProtection
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgskeyprotection/set-hgskeyprotectioncertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-HgsKeyProtectionCertificate
---

# Set-HgsKeyProtectionCertificate

## SYNOPSIS
Modifies properties of a key certificate in the Key Protection Service.

## SYNTAX

```
Set-HgsKeyProtectionCertificate -CertificateType <KeyCertificateType> -Thumbprint <String>
 [-IsEnabled <Boolean>] [-IsPrimary] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-HgsKeyProtectionCertificate** cmdlet modifies properties of a key certificate in the Key Protection Service.
You can make a certificate into the primary certificate.
The primary certificate is used to sign and encrypt new key protectors.
You can enable or disable a certificate.
You can use enabled certificates for either signing or encryption.
A disabled certificate cannot be the primary certificate.

## EXAMPLES

### Example 1: Disable a key certificate
```
PS C:\> Set-HgsKeyProtectionCertificate -CertificateType Signing -Thumbprint "a0e2650e25084961a24da956d132a5fa" -IsEnabled $False
```

This command disables a signing key certificate.

### Example 2: Designate a certificate as the primary certificate
```
PS C:\> Set-HgsKeyProtectionCertificate -CertificateType Encryption -Thumbprint "a17dd68f4ecc499bbe65ee18718123da" -IsPrimary
```

This command designates a certificate as the primary certificate.

## PARAMETERS

### -CertificateType
Specifies of the type of the certificate that this cmdlet modifies.
The acceptable values for this parameter are:

- Signing
- Encryption

```yaml
Type: KeyCertificateType
Parameter Sets: (All)
Aliases:
Accepted values: Signing, Encryption

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

### -IsEnabled
Indicates whether to enable a certificate.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsPrimary
Indicates that this cmdlet makes a certificate into the primary certificate.

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
Specifies the thumbprint of the certificate to modify.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

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

[Add-HgsKeyProtectionCertificate](./Add-HgsKeyProtectionCertificate.md)

[Get-HgsKeyProtectionCertificate](./Get-HgsKeyProtectionCertificate.md)

[Remove-HgsKeyProtectionCertificate](./Remove-HgsKeyProtectionCertificate.md)

