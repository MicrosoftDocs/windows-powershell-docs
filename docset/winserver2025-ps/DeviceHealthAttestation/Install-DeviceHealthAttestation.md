---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.DeviceHealthAttestation.PowerShell.dll-Help.xml
Module Name: DeviceHealthAttestation
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/devicehealthattestation/install-devicehealthattestation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Install-DeviceHealthAttestation
---

# Install-DeviceHealthAttestation

## SYNOPSIS
Installs the Device Health Attestation service.

## SYNTAX

### Install (Default)
```
Install-DeviceHealthAttestation -EncryptionCertificateThumbprint <String>
 -SigningCertificateThumbprint <String> -SupportedAuthenticationSchema <String> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InstallAndAddSslBinding
```
Install-DeviceHealthAttestation -EncryptionCertificateThumbprint <String>
 -SigningCertificateThumbprint <String> -SslCertificateThumbprint <String>
 [-SslCertificateStoreName <StoreName>] -SupportedAuthenticationSchema <String> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Install-DeviceHealthAttestation** cmdlet installs the Device Health Attestation service and configures its dependencies.
Before you can install the service, you must add the Device Health Attestation service role.

The installation does the following:

- Creates an application pool.
- Creates a web application.
- Adds a firewall rule for incoming requests.
- Sets the initial configuration.
- Registers user access logging.

You must have administrator rights to run this cmdlet.

## EXAMPLES

### Example 1: Install the Device Health Attestation service
```
PS C:\> Install-DeviceHealthAttestation -EncryptionCertificateThumbprint "0123456789ABCDEF0123456789ABCDEF01234567" -SigningCertificateThumbprint "0123456789ABCDEF0123456789ABCDEF01234567" -SupportedAuthenticationSchema "AikPub,EkCertificate"
```

This command installs the Device Health Attestation service.

### Example 2: Install the Device Health Attestation service with SSL
```
PS C:\> Install-DeviceHealthAttestation -EncryptionCertificateThumbprint "0123456789ABCDEF0123456789ABCDEF01234567" -SigningCertificateThumbprint "0123456789ABCDEF0123456789ABCDEF01234567" -SupportedAuthenticationSchema "AikPub,EkCertificate" -SslCertificateThumbprint "0123456789ABCDEF0123456789ABCDEF01234567" -SslCertificateStoreName "My"
```

This command installs the Device Health Attestation service with SSL bindings.

## PARAMETERS

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

### -EncryptionCertificateThumbprint
Specifies the encryption certificate thumbprint.
The value must contain only hexadecimal digits (0-9, A-F) and be 40 characters in length.
This value is case-insensitive.

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

### -SigningCertificateThumbprint
Specifies the signing certificate thumbprint.
The value must contain only hexadecimal digits (0-9, A-F) and be 40 characters in length.
This value is case-insensitive.

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

### -SslCertificateStoreName
Specifies the certificate store that contains the certificate referenced by the *SslCertificateThumbprint* parameter.
The acceptable values for this parameter are:

- AddressBook
- AuthRoot
- CertificateAuthority
- Disallowed
- My
- Root
- TrustedPeople
- TrustedPublisher

```yaml
Type: StoreName
Parameter Sets: InstallAndAddSslBinding
Aliases:
Accepted values: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, TrustedPublisher

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SslCertificateThumbprint
Specifies the thumbprint of the certificate to use for server SSL binding.
The value must contain only hexadecimal digits (0-9, A-F) and be 40 characters in length.
This value is case-insensitive.

If you specify *SslCertificateThumbprint*, the cmdlet creates an SSL binding on the default website.
If you specify this parameter, you must also specify the *SslCertificateStoreName* parameter.

```yaml
Type: String
Parameter Sets: InstallAndAddSslBinding
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SupportedAuthenticationSchema
Specifies, in a comma-separated list, the authentication schema that the Device Health Attestation service supports.
The acceptable values for this parameter are:

- AikPub
- AikCertificate
- EkCertificate

You cannot specify both AikCertificate and EkCertificate in the same command.

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Uninstall-DeviceHealthAttestation](./Uninstall-DeviceHealthAttestation.md)

