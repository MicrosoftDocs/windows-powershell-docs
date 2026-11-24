---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Deployment.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/install-adfsfarm?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Install-AdfsFarm
---

# Install-AdfsFarm

## SYNOPSIS
Creates the first node of a new federation server farm.

## SYNTAX

### ADFSFarmCreateLocalDatabase (Default)
```
Install-AdfsFarm [-CertificateThumbprint <String>] [-Credential <PSCredential>] -FederationServiceName <String>
 [-FederationServiceDisplayName <String>] -ServiceAccountCredential <PSCredential> [-OverwriteConfiguration]
 [-SSLPort <Int32>] [-TlsClientPort <Int32>] [-AdminConfiguration <Hashtable>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ADFSFarmCreateLocalDatabaseDisableAutoCertRollover
```
Install-AdfsFarm [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 -DecryptionCertificateThumbprint <String> -FederationServiceName <String>
 [-FederationServiceDisplayName <String>] -ServiceAccountCredential <PSCredential>
 -SigningCertificateThumbprint <String> [-OverwriteConfiguration] [-SSLPort <Int32>] [-TlsClientPort <Int32>]
 [-AdminConfiguration <Hashtable>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ADFSFarmCreateSharedDatabaseDisableAutoCertRollover
```
Install-AdfsFarm [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 -DecryptionCertificateThumbprint <String> -FederationServiceName <String>
 [-FederationServiceDisplayName <String>] -ServiceAccountCredential <PSCredential>
 -SigningCertificateThumbprint <String> -SQLConnectionString <String> [-OverwriteConfiguration]
 [-SSLPort <Int32>] [-TlsClientPort <Int32>] [-AdminConfiguration <Hashtable>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### AdfsFarmCreateLocalDatabaseDisableAutoCertRolloverGmsa
```
Install-AdfsFarm [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 -DecryptionCertificateThumbprint <String> -FederationServiceName <String>
 [-FederationServiceDisplayName <String>] -GroupServiceAccountIdentifier <String>
 -SigningCertificateThumbprint <String> [-OverwriteConfiguration] [-SSLPort <Int32>] [-TlsClientPort <Int32>]
 [-AdminConfiguration <Hashtable>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AdfsFarmCreateSharedDatabaseDisableAutoCertRolloverGmsa
```
Install-AdfsFarm [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 -DecryptionCertificateThumbprint <String> -FederationServiceName <String>
 [-FederationServiceDisplayName <String>] -GroupServiceAccountIdentifier <String>
 -SigningCertificateThumbprint <String> -SQLConnectionString <String> [-OverwriteConfiguration]
 [-SSLPort <Int32>] [-TlsClientPort <Int32>] [-AdminConfiguration <Hashtable>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ADFSFarmCreateSharedDatabase
```
Install-AdfsFarm [-CertificateThumbprint <String>] [-Credential <PSCredential>] -FederationServiceName <String>
 [-FederationServiceDisplayName <String>] -ServiceAccountCredential <PSCredential>
 -SQLConnectionString <String> [-OverwriteConfiguration] [-SSLPort <Int32>] [-TlsClientPort <Int32>]
 [-AdminConfiguration <Hashtable>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AdfsFarmCreateLocalDatabaseGmsa
```
Install-AdfsFarm [-CertificateThumbprint <String>] [-Credential <PSCredential>] -FederationServiceName <String>
 [-FederationServiceDisplayName <String>] -GroupServiceAccountIdentifier <String> [-OverwriteConfiguration]
 [-SSLPort <Int32>] [-TlsClientPort <Int32>] [-AdminConfiguration <Hashtable>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### AdfsFarmCreateSharedDatabaseGmsa
```
Install-AdfsFarm [-CertificateThumbprint <String>] [-Credential <PSCredential>] -FederationServiceName <String>
 [-FederationServiceDisplayName <String>] -GroupServiceAccountIdentifier <String> -SQLConnectionString <String>
 [-OverwriteConfiguration] [-SSLPort <Int32>] [-TlsClientPort <Int32>] [-AdminConfiguration <Hashtable>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Install-AdfsFarm** cmdlet creates the first node of a new federation server farm.

## EXAMPLES

### Example 1: Create the first node in a federation server farm using WID on the local server
```
PS C:\> $fscredential = Get-Credential
PS C:\> Install-AdfsFarm -CertificateThumbprint 8169c52b4ec6e77eb2ae17f028fe5da4e35c0bed -FederationServiceName fs.corp.contoso.com -ServiceAccountCredential $fscredential
```

Creates the first node in a federation server farm that uses the Windows Internal Database (WID) on the local server computer.

In this example, a certificate thumbprint value is supplied for the *CertificateThumbprint* parameter.
This certificate will be used as the SSL certificate and the service communications certificate.
Automatically generated, self-signed certificates will be used for the token signing and token decryption certificates.

To specify certificates for token signing and token decryption, specify thumbprint values for the *SigningCertificateThumbprint* and *DecryptionCertificateThumbprint* parameters.

### Example 2: Create the first node in a federation server farm using a group Managed Services Account
```
PS C:\> Install-AdfsFarm -CertificateThumbprint 8169c52b4ec6e77eb2ae17f028fe5da4e35c0bed -FederationServiceName fs.corp.contoso.com -GroupServiceAccountIdentifier CONTOSO\GroupAccount01
```

This example creates the first node in a federation server farm that uses a group Managed Service Account as the service account.
In this example, a certificate thumbprint value is supplied for the *CertificateThumbprint* parameter.
This certificate will be used as the SSL certificate and the service communications certificate.
Automatically generated, self-signed certificates will be used for the token signing and token decryption certificates.
To specify certificates for token signing and token decryption, specify thumbprint values for the *SigningCertificateThumbprint* and *DecryptionCertificateThumbprint* parameters.

### Example 3: Create the first node in a federation server farm that uses SQL Server on a remote computer
```
PS C:\> $fscredential = Get-Credential
PS C:\> Install-AdfsFarm -CertificateThumbprint 8169c52b4ec6e77eb2ae17f028fe5da4e35c0bed -FederationServiceName fs.corp.contoso.com -ServiceAccountCredential $fscredential -SQLConnectionString "Data Source=SQLHost;Integrated Security=True"
```

Creates the first node in a federation server farm that uses a Microsoft SQL Server database on a remote computer named SQLHost.

In this example, a certificate thumbprint value is supplied for the *CertificateThumbprint* parameter.
This certificate will be used as the SSL certificate and the service communications certificate.
Automatically generated, self-signed certificates will be used for the token signing and token decryption certificates.

To specify certificates for token signing and token decryption, specify thumbprint values for the *SigningCertificateThumbprint* and *DecryptionCertificateThumbprint* parameters.

### Example 4: Overwrite an AD FS configuration and create the first node in a federation server farm
```
PS C:\> $fscredential = Get-Credential
PS C:\> Install-AdfsFarm -CertificateThumbprint 8169c52b4ec6e77eb2ae17f028fe5da4e35c0bed -FederationServiceName fs.corp.contoso.com -ServiceAccountCredential $fscredential -SQLConnectionString "Data Source=SQLHost;Integrated Security=True" -OverwriteConfiguration -SigningCertificateThumbprint 8169c52b4ec6e77eb2ae17f028fe5da4e35c0bed -DecryptionCertificateThumbprint cf2e5064c521d625c8d53536bc98aa8e08f5f2ad
```

Overwrites an existing AD FS configuration database and creates the first node in a federation server farm that uses a Microsoft SQL server database on a remote computer named SQLHost.

In this example, certificate thumbprint values are specified for the token signing certificate and for the token encryption certificate using the *SigningCertificateThumbprint* and *DecryptionCertificateThumbprint* parameters respectively.



## PARAMETERS

### -AdminConfiguration (Currently not supported)
```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint
Specifies the certificate thumbprint of a digital public key X.509 certificate of a user account that has permission to perform this action.

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

### -Credential
Specifies a **PSCredential** object.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DecryptionCertificateThumbprint
Specifies the value of the certificate thumbprint of the certificate that should be used for token decryption.
If this parameter is used, the automatic certificate rollover feature will be disabled, and a token signing certificate must also be specified using the *SigningCertificateThumbprint* parameter.
This value should match the thumbprint of a valid certificate in the Local Computer certificate store.

```yaml
Type: String
Parameter Sets: ADFSFarmCreateLocalDatabaseDisableAutoCertRollover, ADFSFarmCreateSharedDatabaseDisableAutoCertRollover, AdfsFarmCreateLocalDatabaseDisableAutoCertRolloverGmsa, AdfsFarmCreateSharedDatabaseDisableAutoCertRolloverGmsa
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FederationServiceDisplayName
Specifies a display name.

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

### -FederationServiceName
Specifies a Federation Service name.

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

### -GroupServiceAccountIdentifier
Specifies the Group Managed Service Account under which the Active Directory Federation Services (AD FS) service runs.

```yaml
Type: String
Parameter Sets: AdfsFarmCreateLocalDatabaseDisableAutoCertRolloverGmsa, AdfsFarmCreateSharedDatabaseDisableAutoCertRolloverGmsa, AdfsFarmCreateLocalDatabaseGmsa, AdfsFarmCreateSharedDatabaseGmsa
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverwriteConfiguration
Overwrites an existing AD FS configuration database with a new database.

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

### -ServiceAccountCredential
Specifies the Active Directory account under which the AD FS service runs.

```yaml
Type: PSCredential
Parameter Sets: ADFSFarmCreateLocalDatabase, ADFSFarmCreateLocalDatabaseDisableAutoCertRollover, ADFSFarmCreateSharedDatabaseDisableAutoCertRollover, ADFSFarmCreateSharedDatabase
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SigningCertificateThumbprint
Specifies the value of the certificate thumbprint of the certificate that should be used for token signing.
If this parameter is used, the automatic certificate rollover feature will be disabled, and a token decryption certificate must also be specified using the *DecryptionCertificateThumbprint* parameter.
This value should match the thumbprint of a valid certificate in the Local Computer certificate store.

```yaml
Type: String
Parameter Sets: ADFSFarmCreateLocalDatabaseDisableAutoCertRollover, ADFSFarmCreateSharedDatabaseDisableAutoCertRollover, AdfsFarmCreateLocalDatabaseDisableAutoCertRolloverGmsa, AdfsFarmCreateSharedDatabaseDisableAutoCertRolloverGmsa
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SQLConnectionString
Specifies the SQL Server database that will store the AD FS configuration settings.
If not specified, the AD FS installer uses the Windows Internal Database to store configuration settings.

```yaml
Type: String
Parameter Sets: ADFSFarmCreateSharedDatabaseDisableAutoCertRollover, AdfsFarmCreateSharedDatabaseDisableAutoCertRolloverGmsa, ADFSFarmCreateSharedDatabase, AdfsFarmCreateSharedDatabaseGmsa
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SSLPort
Specifies an SSL port.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TlsClientPort
Specifies a TLS client port.

```yaml
Type: Int32
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

## OUTPUTS

## NOTES

## RELATED LINKS

