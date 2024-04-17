---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.KpsServer.Administration.dll-Help.xml
Module Name: HgsKeyProtection
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgskeyprotection/add-hgskeyprotectioncertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-HgsKeyProtectionCertificate
---

# Add-HgsKeyProtectionCertificate

## SYNOPSIS
Adds a key certificate to the Key Protection Service.

## SYNTAX

### CertificateReference (Default)
```
Add-HgsKeyProtectionCertificate -CertificateType <KeyCertificateType> -Thumbprint <String>
 [-NoCertificateReplication] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FullCertificate
```
Add-HgsKeyProtectionCertificate -CertificateType <KeyCertificateType> -CertificatePath <String>
 [-CertificatePassword <SecureString>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-HgsKeyProtectionCertificate** cmdlet adds a certificate to the Key Protection Service.
You can add a certificate as an encryption certificate or a signing certificate.
You can add a reference to a certificate stored in the Windows certificate store.
Before you add a certificate reference you must add the certificate to the LocalMachine\My certificate store.
The cmdlet looks up the certificate in the LocalMachine\My certificate store by using its thumbprint.
You can also add a full certificate stored in a file as a pfx.
If the file containing the pfx is protected by a password, you must specify the pfx password.

## EXAMPLES

### Example 1: Add an encryption certificate
```
PS C:\> Add-HgsKeyProtectionCertificate -CertificateType Encryption -Thumbprint "d39203a3b3544743ad552afe0615dc1f"
```

This command adds a certificate reference to the Key Protection Service for use as an encryption certificate.

### Example 2: Add an encryption certificate file with a password
```
PS C:\> Add-HgsKeyProtectionCertificate -CertificateType Encryption -CertificatePath "C:\example.pfx" -CertificatePassword $Password
```

This command adds a certificate file to the Key Protection Service as an encryption certificate.
In this example, the certificate file is protected by a password stored as a SecureString in the variable $Password.

## PARAMETERS

### -CertificatePassword
Specifies the password which protects a certificate file.
If the certificate file is protected by a password, you must specify this value.

```yaml
Type: SecureString
Parameter Sets: FullCertificate
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificatePath
Specifies the path to the certificate which will be added to the Key Protection Service.

```yaml
Type: String
Parameter Sets: FullCertificate
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateType
Specifies the type of the certificate that this cmdlet adds.
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

### -NoCertificateReplication
This only applies when you use the `-Thumbprint` option to specify a certificate.
It is typically used for hardware security module (HSM) backed certificates but can be used for other certificates too.
Specifying `NoCertificateReplication` disables automatic replication of the certificate from LocalMachine\My certificate store to the same store on all other nodes in the cluster.
The HGS admin is then responsible for replicating that certificate manually to all other nodes in the cluster.

```yaml
Type: SwitchParameter
Parameter Sets: CertificateReference
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Thumbprint
Specifies the thumbprint of the certificate to add.
You must add the certificate to the LocalMachine\My certificate store before you run the current cmdlet.

```yaml
Type: String
Parameter Sets: CertificateReference
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

[Get-HgsKeyProtectionCertificate](./Get-HgsKeyProtectionCertificate.md)

[Remove-HgsKeyProtectionCertificate](./Remove-HgsKeyProtectionCertificate.md)

[Set-HgsKeyProtectionCertificate](./Set-HgsKeyProtectionCertificate.md)

