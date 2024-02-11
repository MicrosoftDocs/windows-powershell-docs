---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: HgsClient-help.xml
Module Name: HgsClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgsclient/new-hgsguardian?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-HgsGuardian
---

# New-HgsGuardian

## SYNOPSIS
Creates a Host Guardian Service guardian.

## SYNTAX

### AcceptCertificates
```
New-HgsGuardian [-Name] <String> -SigningCertificate <String> [-SigningCertificatePassword <SecureString>]
 -EncryptionCertificate <String> [-EncryptionCertificatePassword <SecureString>] [-AllowExpired]
 [-AllowUntrustedRoot] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByThumbprints
```
New-HgsGuardian [-Name] <String> [-AllowExpired] [-AllowUntrustedRoot] -SigningCertificateThumbprint <String>
 -EncryptionCertificateThumbprint <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### GenerateCertificates
```
New-HgsGuardian [-Name] <String> [-GenerateCertificates] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-HgsGuardian** cmdlet creates a cryptographic entity called a Host Guardian Service guardian.
A guardian is a principal that you can grant access to the key that is contained in a key protector.

## EXAMPLES

### Example 1: Create a guardian
```
PS C:\> New-HgsGuardian -Name "Guardian11" -GenerateCertificates
```

This command creates a Host Guardian Service guardian named Guardian11.
This guardian can act as owner for a key protector.
Because this command specifies the **GenerateCertificates** parameter, it generates signing and encryption certificates.

### Example 2: Create a guardian by using existing certificates
```
PS C:\> $SecureStringPassword01 = ConvertTo-SecureString "<Password01>" -AsPlainText -Force
PS C:\> $SecureStringPassword02 = ConvertTo-SecureString "<Password02>" -AsPlainText -Force
PS C:\> New-HgsGuardian -Name "Guardian21" -SigningCertificate "C:\Keys\SigningCertificate.pfx" -SigningCertificatePassword $SecureStringPassword01 -EncryptionCertificate "C:\Keys\EncryptionCertificate.pfx" -EncryptionCertificatePassword $SecureStringPassword02
```

The first two commands create passwords, as secure strings, by using the **ConvertTo-SecureString** cmdlet.
For more information, type `Get-Help ConvertTo-SecureString`.
The commands store the passwords in two variables.

The final command creates a guardian named Guardian21.
The command specifies the necessary signing and encryption certificates as password protected .pfx files.
The passwords stored in the **$SecureStringPassword01** and **$SecureStringPassword02** must match the passwords used to generate the .pfx files.

## PARAMETERS

### -AllowExpired
Indicates that this cmdlet can create a guardian by using certificates that are expired.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AcceptCertificates, ByThumbprints
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowUntrustedRoot
Indicates that this cmdlet can create a guardian by using self-signed certificates.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AcceptCertificates, ByThumbprints
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionCertificate
Specifies the path of a .pfx file that contains a password protected encryption certificate for the guardian.
This .pfx file contains the public and private keys.

```yaml
Type: String
Parameter Sets: AcceptCertificates
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionCertificatePassword
Specifies the password to decrypt the .pfx file that contains the encryption certificate.

```yaml
Type: SecureString
Parameter Sets: AcceptCertificates
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionCertificateThumbprint
Specifies the encryption certificate thumbprint.

```yaml
Type: String
Parameter Sets: ByThumbprints
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GenerateCertificates
Indicates that this cmdlet generates self-signed signing and encryption certificates for the guardian.
The certificates contain the public and private keys.

If you specify this parameter, the new guardian does not have a trusted root.
Therefore, you must also specify the **AllowUntrustedRoot** parameter.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenerateCertificates
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a name for the new guardian.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SigningCertificate
Specifies the path of a .pfx file that contains a password protected signing certificate for the guardian.
This .pfx file contains the public and private keys.

```yaml
Type: String
Parameter Sets: AcceptCertificates
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SigningCertificatePassword
Specifies the password necessary to decrypt the signing certificate .pfx file.

```yaml
Type: SecureString
Parameter Sets: AcceptCertificates
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SigningCertificateThumbprint
Specifies the thumbprint of a signing certificate located in the local computer certificate store.

```yaml
Type: String
Parameter Sets: ByThumbprints
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
Type: System.Management.Automation.SwitchParameter
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
Type: System.Management.Automation.SwitchParameter
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

## OUTPUTS

### CimInstance#MSFT_HgsGuardian
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Export-HgsGuardian](./Export-HgsGuardian.md)

[Get-HgsGuardian](./Get-HgsGuardian.md)

[Import-HgsGuardian](./Import-HgsGuardian.md)

[Remove-HgsGuardian](./Remove-HgsGuardian.md)

