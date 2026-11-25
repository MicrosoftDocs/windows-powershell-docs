---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: HgsServer-help.xml
Module Name: HgsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgsserver/initialize-hgsserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Initialize-HgsServer
---

# Initialize-HgsServer

## SYNOPSIS
Initializes the Host Guardian Service server.

## SYNTAX

### PrimaryServer_HgsDomain (Default)
```
Initialize-HgsServer [-HgsServiceName] <String> [-UseHgsDomain] [-LogDirectory <String>] [-Http] [-Https]
 [-HttpPort <UInt16>] [-HttpsPort <UInt16>] [-HttpsCertificatePath <String>]
 [-HttpsCertificatePassword <SecureString>] [-HttpsCertificateThumbprint <String>] [-TrustActiveDirectory]
 [-TrustTpm] [-EncryptionCertificateThumbprint <String>] [-EncryptionCertificatePath <String>]
 [-EncryptionCertificatePassword <SecureString>] [-SigningCertificateThumbprint <String>]
 [-SigningCertificatePath <String>] [-SigningCertificatePassword <SecureString>] [-HgsVersion <HgsVersion>]
 [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### PrimaryServer_SecureDomain
```
Initialize-HgsServer [-HgsServiceName] <String> [-UseExistingDomain] [-LogDirectory <String>]
 -JeaAdministratorsGroup <ADGroup> -JeaReviewersGroup <ADGroup> -ServiceAccount <ADServiceAccount>
 [-ClusterName <String>] [-Http] [-Https] [-HttpPort <UInt16>] [-HttpsPort <UInt16>]
 [-HttpsCertificatePath <String>] [-HttpsCertificatePassword <SecureString>]
 [-HttpsCertificateThumbprint <String>] [-TrustActiveDirectory] [-TrustTpm]
 [-EncryptionCertificateThumbprint <String>] [-EncryptionCertificatePath <String>]
 [-EncryptionCertificatePassword <SecureString>] [-SigningCertificateThumbprint <String>]
 [-SigningCertificatePath <String>] [-SigningCertificatePassword <SecureString>] [-HgsVersion <HgsVersion>]
 [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AdditionalServer
```
Initialize-HgsServer [-HgsServerIPAddress] <String> [-LogDirectory <String>] [-Http] [-Https]
 [-HttpPort <UInt16>] [-HttpsPort <UInt16>] [-HttpsCertificatePath <String>]
 [-HttpsCertificatePassword <SecureString>] [-HttpsCertificateThumbprint <String>] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Initialize-HgsServer** cmdlet configures the necessary infrastructure components for Host Guardian Service (HGS) after it is rebooted.

This cmdlet performs the following configuration actions on infrastructure components of the first HGS node:

- Creates one-node failover cluster.
- Configures a failover cluster with a distributed network name resource corresponding to the fully qualified domain name of the HGS name: \<HgsServerName\>.\<LocalDomain\>.
- Registers and configures the Attestation service web application with the IIS service.
- Registers and configures the Key Protection service web application with the IIS service.
- Configures the Attestation service signer certificate with the Key Protection service.
- Enables Just Enough Administration on the local node.

This cmdlet makes the following configuration changes to components on an additional HGS node:

- Adds the local node to the existing failover cluster on a node specified by the **HgsServerIPAddress** parameter using the credential specified in the **HgsDomainCredential** parameter.

- Registers and configures the Attestation service web application with the IIS service.
- Registers and configures the Key Protection service web application with the IIS service.
- Configures the Attestation service signer certificate with the Key Protection service.
- Enables Just Enough Administration on the local node.

For more information about the scenario terms, see [Security and Assurance](https://go.microsoft.com/fwlink/?LinkId=699209).

## EXAMPLES

### Example 1: Initialize the HGS on the primary node in TPM mode
```
PS C:\> Initialize-HgsServer -HgsServiceName "SecureFabricHgs" -EncryptionCertificateThumbprint $EncryptionCert.Thumbprint -SigningCertificateThumbprint $SigningCert.Thumbprint
```

This command initializes the HGS server on the primary node.
By default, the server is accessible on HTTP port 80 and the Attestation service is set to TPM mode.
The specified certificates are used by the Key Protection service.

### Example 2: Initialize the HGS on a secondary node in TPM mode
```
PS C:\> $Cred = Get-Credential
PS C:\> Initialize-HgsServer -HgsServerIPAddress "100.100.100.1" -HgsDomainCredential $Cred
```

This command initializes the HGS server on a secondary node.
By default, the server is accessible on HTTP port 80 and the Attestation service is set to TPM mode.
The Key Protection service uses the encryption and signing certificates set by the primary server.

### Example 3: Initialize the HGS on the primary node in Active Directory mode
```
PS C:\> Initialize-HgsServer -TrustActiveDirectory -HgsServiceName "SecureFabricHgs" -EncryptionCertificateThumbprint $EncryptionCert.Thumbprint -SigningCertificateThumbprint $SigningCert.Thumbprint
```

This command initializes the HGS server on the primary node and sets the Attestation service to Active Directory (AD) mode.
By default, the server is accessible on HTTP port 80.
The specified certificates are used by the Key Protection service.

### Example 4: Initialize the HGS on the primary node in TPM mode and enable HTTPS
```
PS C:\> Initialize-HgsServer -HgsServiceName "SecureFabricHgs" -EncryptionCertificateThumbprint $EncryptionCert.Thumbprint -SigningCertificateThumbprint $SigningCert.Thumbprint -http -https -HttpsCertificatePath $PathToPfx -HttpsCertificatePassword $PfxSecureString
```

This command initializes the HGS server on the primary node.
The server is set to be accessible by HTTP and HTTPS on the default ports, and with the specified certificate for HTTPS.
By default, the server is accessible on HTTP port 80 and the Attestation service is set to TPM mode.
The specified certificates are used by the Key Protection service.

## PARAMETERS

### -ClusterName
Specifies a cluster name.

```yaml
Type: String
Parameter Sets: PrimaryServer_SecureDomain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionCertificatePassword
Specifies the password for the certificate file specified in **EncryptionCertificatePath**.

```yaml
Type: SecureString
Parameter Sets: PrimaryServer_HgsDomain, PrimaryServer_SecureDomain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionCertificatePath
Specifies the path to the encryption certificate used by the Key Protection service.

```yaml
Type: String
Parameter Sets: PrimaryServer_HgsDomain, PrimaryServer_SecureDomain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionCertificateThumbprint
Specifies the thumbprint of the encryption certificate used by the Key Protection service.

```yaml
Type: String
Parameter Sets: PrimaryServer_HgsDomain, PrimaryServer_SecureDomain
Aliases:

Required: False
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

### -HgsServerIPAddress
Specifies the IP address of the HGS server that is a domain controller for the specified HGS domain.

```yaml
Type: String
Parameter Sets: AdditionalServer
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HgsServiceName
Specifies the HGS name.

```yaml
Type: String
Parameter Sets: PrimaryServer_HgsDomain, PrimaryServer_SecureDomain
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HgsVersion
Reserved for future use.

```yaml
Type: HgsVersion
Parameter Sets: PrimaryServer_HgsDomain, PrimaryServer_SecureDomain
Aliases:
Accepted values: HgsVersion1503, HgsVersion1704

Required: False
Position: Named
Default value: $script:HgsSupportedLevels[0]
Accept pipeline input: False
Accept wildcard characters: False
```

### -Http
Indicates that the HGS server is accessible over HTTP.

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

### -HttpPort
Specifies the HTTP port of the HGS server.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Https
Indicates that the HGS server is accessible over HTTPS.

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

### -HttpsCertificatePassword
Specifies the password to the certificate file identified by **HttpsCertificatePath**.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HttpsCertificatePath
Specifies the path to the HTTPS certificate file (.pfx).

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HttpsCertificateThumbprint
Indicates the thumbprint of the HTTPS certificate.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HttpsPort
Specifies the HTTPS port of the HGS server.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JeaAdministratorsGroup
Identifies the Active Directory group of users who can administer HGS through Just Enough Administration.

```yaml
Type: ADGroup
Parameter Sets: PrimaryServer_SecureDomain
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JeaReviewersGroup
Identifies the Active Directory group of users who can view, but not change, HGS settings through Just Enough Administration.

```yaml
Type: ADGroup
Parameter Sets: PrimaryServer_SecureDomain
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogDirectory
Specifies the directory for the output log.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceAccount
Identifies the Group Managed Service Account that will be used for the Key Protection Service. The specified account must already be installed and configured for use on this machine.

```yaml
Type: ADServiceAccount
Parameter Sets: PrimaryServer_SecureDomain
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SigningCertificatePassword
Specifies the password for the certificate file identified by **SigningCertificatePath**.

```yaml
Type: SecureString
Parameter Sets: PrimaryServer_HgsDomain, PrimaryServer_SecureDomain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SigningCertificatePath
Specifies the path to the signing certificate for use by the Key Protection service.

```yaml
Type: String
Parameter Sets: PrimaryServer_HgsDomain, PrimaryServer_SecureDomain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SigningCertificateThumbprint
Specifies the thumbprint of the signing certificate for use by the Key Protection service.

```yaml
Type: String
Parameter Sets: PrimaryServer_HgsDomain, PrimaryServer_SecureDomain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrustActiveDirectory
```yaml
Type: SwitchParameter
Parameter Sets: PrimaryServer_HgsDomain, PrimaryServer_SecureDomain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrustTpm
```yaml
Type: SwitchParameter
Parameter Sets: PrimaryServer_HgsDomain, PrimaryServer_SecureDomain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseExistingDomain
Indicates that HGS was joined to an existing domain and did not establish its own domain (with Install-HgsServer). HGS must already be joined to the existing domain to continue.

```yaml
Type: SwitchParameter
Parameter Sets: PrimaryServer_SecureDomain
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseHgsDomain
Indicates that HGS was set up with its own dedicated Active Directory forest using the Install-HgsServer cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: PrimaryServer_HgsDomain
Aliases:

Required: False
Position: Named
Default value: False
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

## OUTPUTS

## NOTES

## RELATED LINKS

[HGS Server Cmdlets](./hgsserver.md)

