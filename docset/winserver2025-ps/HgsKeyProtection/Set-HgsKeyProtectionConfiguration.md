---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.KpsServer.Administration.dll-Help.xml
Module Name: HgsKeyProtection
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgskeyprotection/set-hgskeyprotectionconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-HgsKeyProtectionConfiguration
---

# Set-HgsKeyProtectionConfiguration

## SYNOPSIS
Modifies the configuration of the Key Protection Service.

## SYNTAX

### CertificateReference (Default)
```
Set-HgsKeyProtectionConfiguration -CommunicationsCertificateThumbprint <String>
 [-NoCommunicationsCertificateReplication] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FullCertificate
```
Set-HgsKeyProtectionConfiguration -CommunicationsCertificatePath <String>
 [-CommunicationsCertificatePassword <SecureString>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-HgsKeyProtectionConfiguration** cmdlet assigns a communication certificate to the Key Protection Service that runs on the local computer.
The Key Protection Service uses the communication certificate to sign the metadata document that the service provides.

## EXAMPLES

### Example 1: Assign a certificate to be the communication certificate
```
PS C:\> Set-HgsKeyProtectionConfiguration -CommunicationsCertificateThumbprint "d39203a3b3544743ad552afe0615dc1f" -Force
```

This command assigns the certificate that has the specified thumbprint to be the communication certificate for the Key Protection Service.
The command specifies the **Force**, and so, it does not prompt you for confirmation.

### Example 2: Assign a certificate file to be the communications certificate
```
PS C:\> Set-HgsKeyProtectionConfiguration -CommunicationsCertificatePath "C:\example.pfx"
Set-HgsKeyProtectionConfiguration -CommunicationsCertificateThumbprint "d39203a3b3544743ad552afe0615dc1f" -Force
```

This command assigns a certificate file to be the communications certificate for the Key Protection Service.

### Example 3: Assign a certificate file with a password to be the communications certificate
```
PS C:\> Set-HgsKeyProtectionConfiguration -CommunicationsCertificatePath "C:\example.pfx" -CommunicationsCertificatePassword $Password
```

This command assigns a password-protected certificate file to be the communications certificate for the Key Protection Service.
The certificate password is stored as a SecureString in the **$Password** variable.

## PARAMETERS

### -CommunicationsCertificatePassword
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

### -CommunicationsCertificatePath
Specifies the path to the certificate which will be added to the Key Protection Service as the communications certificate.

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

### -CommunicationsCertificateThumbprint
Specifies the thumbprint of the new communications certificate.
Before you run this cmdlet, the certificate that this parameter specifies needs to already be in the LocalMachine\My certificate store.

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

### -NoCommunicationsCertificateReplication
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

[Get-HgsKeyProtectionConfiguration](./Get-HgsKeyProtectionConfiguration.md)

