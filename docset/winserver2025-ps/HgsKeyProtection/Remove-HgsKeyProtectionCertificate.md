---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.KpsServer.Administration.dll-Help.xml
Module Name: HgsKeyProtection
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgskeyprotection/remove-hgskeyprotectioncertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-HgsKeyProtectionCertificate
---

# Remove-HgsKeyProtectionCertificate

## SYNOPSIS
Removes a key certificate from the Key Protection Service.

## SYNTAX

```
Remove-HgsKeyProtectionCertificate -CertificateType <KeyCertificateType> -Thumbprint <String> [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HgsKeyProtectionCertificate** cmdlet removes a key certificate from the Key Protection Service.
If the certificate being removed references a certificate stored in the LocalMachine\My certificate store, this cmdlet does not delete that certificate from the LocalMachine\My certificate store.

## EXAMPLES

### Example 1: Remove an encryption certificate
```
PS C:\> Remove-HgsKeyProtectionCertificate -CertificateType Encryption -Thumbprint "d39203a3b3544743ad552afe0615dc1f"
```

This command removes an encryption certificate from the Key Protection Service.

## PARAMETERS

### -CertificateType
Specifies of the type of the certificate that this cmdlet removes.
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

### -Thumbprint
Specifies the thumbprint of the certificate to remove.

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

[Set-HgsKeyProtectionCertificate](./Set-HgsKeyProtectionCertificate.md)

