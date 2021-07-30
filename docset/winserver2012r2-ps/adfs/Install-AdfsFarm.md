---
external help file: Microsoft.IdentityServer.Deployment.dll-Help.xml
Module Name: ADFS
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/adfs/install-adfsfarm?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
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
 [-SSLPort <Int32>] [-TlsClientPort <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ADFSFarmCreateLocalDatabaseDisableAutoCertRollover
```
Install-AdfsFarm [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 -DecryptionCertificateThumbprint <String> -FederationServiceName <String>
 [-FederationServiceDisplayName <String>] -ServiceAccountCredential <PSCredential>
 -SigningCertificateThumbprint <String> [-OverwriteConfiguration] [-SSLPort <Int32>] [-TlsClientPort <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AdfsFarmCreateLocalDatabaseDisableAutoCertRolloverGmsa
```
Install-AdfsFarm [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 -DecryptionCertificateThumbprint <String> -FederationServiceName <String>
 [-FederationServiceDisplayName <String>] -GroupServiceAccountIdentifier <String>
 -SigningCertificateThumbprint <String> [-OverwriteConfiguration] [-SSLPort <Int32>] [-TlsClientPort <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AdfsFarmCreateSharedDatabaseDisableAutoCertRolloverGmsa
```
Install-AdfsFarm [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 -DecryptionCertificateThumbprint <String> -FederationServiceName <String>
 [-FederationServiceDisplayName <String>] -GroupServiceAccountIdentifier <String>
 -SigningCertificateThumbprint <String> -SQLConnectionString <String> [-OverwriteConfiguration]
 [-SSLPort <Int32>] [-TlsClientPort <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ADFSFarmCreateSharedDatabaseDisableAutoCertRollover
```
Install-AdfsFarm [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 -DecryptionCertificateThumbprint <String> -FederationServiceName <String>
 [-FederationServiceDisplayName <String>] -ServiceAccountCredential <PSCredential>
 -SigningCertificateThumbprint <String> -SQLConnectionString <String> [-OverwriteConfiguration]
 [-SSLPort <Int32>] [-TlsClientPort <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ADFSFarmCreateSharedDatabase
```
Install-AdfsFarm [-CertificateThumbprint <String>] [-Credential <PSCredential>] -FederationServiceName <String>
 [-FederationServiceDisplayName <String>] -ServiceAccountCredential <PSCredential>
 -SQLConnectionString <String> [-OverwriteConfiguration] [-SSLPort <Int32>] [-TlsClientPort <Int32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### AdfsFarmCreateSharedDatabaseGmsa
```
Install-AdfsFarm [-CertificateThumbprint <String>] [-Credential <PSCredential>] -FederationServiceName <String>
 [-FederationServiceDisplayName <String>] -GroupServiceAccountIdentifier <String> -SQLConnectionString <String>
 [-OverwriteConfiguration] [-SSLPort <Int32>] [-TlsClientPort <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### AdfsFarmCreateLocalDatabaseGmsa
```
Install-AdfsFarm [-CertificateThumbprint <String>] [-Credential <PSCredential>] -FederationServiceName <String>
 [-FederationServiceDisplayName <String>] -GroupServiceAccountIdentifier <String> [-OverwriteConfiguration]
 [-SSLPort <Int32>] [-TlsClientPort <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Install-AdfsFarm** cmdlet creates the first node of a new federation server farm.

## EXAMPLES

### Example 1
```
PS C:\> $fscredential = Get-Credential
PS C:\> Install-AdfsFarm -CertificateThumbprint 8169c52b4ec6e77eb2ae17f028fe5da4e35c0bed -FederationServiceName fs.corp.contoso.com -ServiceAccountCredential $fscredential
```

Description

Creates the first node in a federation server farm that uses the Windows Internal Database (WID) on the local server computer.

In this example, a certificate thumbprint value is supplied for the CertificateThumbprint parameter. 
This certificate will be used as the SSL certificate and the service communications certificate. 
Automatically generated, self-signed certificates will be used for the token signing and token decryption certificates.

To specify certificates for token signing and token decryption, specify thumbprint values for the SigningCertificateThumbprint and DecryptionCertificateThumbprint parameters.

### Example 2
```
PS C:\> Install-AdfsFarm -CertificateThumbprint 8169c52b4ec6e77eb2ae17f028fe5da4e35c0bed -FederationServiceName fs.corp.contoso.com -GroupServiceAccountIdentifier CONTOSO\GroupAccount01
```

Description

This example creates the first node in a federation server farm that uses a group Managed Service Account as the service account.
In this example, a certificate thumbprint value is supplied for the CertificateThumbprint parameter. 
This certificate will be used as the SSL certificate and the service communications certificate. 
Automatically generated, self-signed certificates will be used for the token signing and token decryption certificates.To specify certificates for token signing and token decryption, specify thumbprint values for the SigningCertificateThumbprint and DecryptionCertificateThumbprint parameters

Lists thumbprint values of currently installed certificates.

### Example 3
```
PS C:\> $fscredential = Get-Credential
PS C:\> Install-AdfsFarm -CertificateThumbprint 8169c52b4ec6e77eb2ae17f028fe5da4e35c0bed -FederationServiceName fs.corp.contoso.com -ServiceAccountCredential $fscredential -SQLConnectionString "Data Source=SQLHost;Integrated Security=True"
```

Description

-----------

Creates the first node in a federation server farm that uses a Microsoft SQL server database on a remote computer named "SQLHost".

In this example, a certificate thumbprint value is supplied for the CertificateThumbprint parameter. 
This certificate will be used as the SSL certificate and the service communications certificate. 
Automatically generated, self-signed certificates will be used for the token signing and token decryption certificates.

To specify certificates for token signing and token decryption, specify thumbprint values for the SigningCertificateThumbprint and DecryptionCertificateThumbprint parameters.

### Example 4
```
PS C:\> $fscredential = Get-Credential
PS C:\> Install-AdfsFarm -CertificateThumbprint 8169c52b4ec6e77eb2ae17f028fe5da4e35c0bed -FederationServiceName fs.corp.contoso.com -ServiceAccountCredential $fscredential -SQLConnectionString "Data Source=SQLHost;Integrated Security=True" -OverwriteConfiguration -SigningCertificateThumbprint 8169c52b4ec6e77eb2ae17f028fe5da4e35c0bed -DecryptionCertificateThumbprint cf2e5064c521d625c8d53536bc98aa8e08f5f2ad
```

Description

-----------

Overwrites an existing AD FS configuration database and creates the first node in a federation server farm that uses a Microsoft SQL server database on a remote computer named "SQLHost".

In this example, certificate thumbprint values are specified for the token signing certificate and for the token encryption certificate using the SigningCertificateThumbprint and DecryptionCertificateThumbprint parameters respectively.

## PARAMETERS

### -CertificateThumbprint
Specifies the value of the certificate thumbprint of the certificate that should be used in the Secure Sockets Layer (SSL) binding of the Default Web Site in Internet Information Services (IIS).
This value should match the thumbprint of a valid certificate in the Local Computer certificate store.

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

### -Credential
Specifies a **PSCredential** object based on a user name and password.
To obtain a **PSCredential** object, use the Get-Credentialhttps://go.microsoft.com/fwlink/?LinkID=293936 cmdlet.
For more information, type `Get-Help Get-Credential`.
To use this cmdlet, you must supply credentials that have domain administrator privileges.

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
If this parameter is used, the automatic certificate rollover feature will be disabled, and a token signing certificate must also be specified using the SigningCertificateThumbprint parameter.
This value should match the thumbprint of a valid certificate in the Local Computer certificate store.

```yaml
Type: String
Parameter Sets: ADFSFarmCreateLocalDatabaseDisableAutoCertRollover, AdfsFarmCreateLocalDatabaseDisableAutoCertRolloverGmsa, AdfsFarmCreateSharedDatabaseDisableAutoCertRolloverGmsa, ADFSFarmCreateSharedDatabaseDisableAutoCertRollover
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FederationServiceDisplayName
Specifies the display name of the Federation Service.
The name that you specify is the organization for which this Federation Service issues tokens.
For instance, you might specify Contoso Corporation.
If you do not specify a value for this parameter, the Federation Service uses the value specified by the **FederationServiceName** parameter.

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
Specifies the DNS name of the federation service.
This value must match the subject name of the certificate configured on the SSL binding in IIS.

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
Parameter Sets: AdfsFarmCreateLocalDatabaseDisableAutoCertRolloverGmsa, AdfsFarmCreateSharedDatabaseDisableAutoCertRolloverGmsa, AdfsFarmCreateSharedDatabaseGmsa, AdfsFarmCreateLocalDatabaseGmsa
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverwriteConfiguration
This parameter must be used to remove an existing Active Directory Federation Services (AD FS) configuration database and overwrite it with a new database.

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

### -SQLConnectionString
Specifies the SQL Server database that will store the AD FS configuration settings. 
If not specified, the AD FS installer uses the Windows Internal Database to store configuration settings.

```yaml
Type: String
Parameter Sets: AdfsFarmCreateSharedDatabaseDisableAutoCertRolloverGmsa, ADFSFarmCreateSharedDatabaseDisableAutoCertRollover, ADFSFarmCreateSharedDatabase, AdfsFarmCreateSharedDatabaseGmsa
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SSLPort
Specifies the value of the port number of the SSL binding that the AD FS web site will use.

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
If this parameter is used, the automatic certificate rollover feature will be disabled, and a token decryption certificate must also be specified using the DecryptionCertificateThumbprint parameter.
This value should match the thumbprint of a valid certificate in the Local Computer certificate store.

```yaml
Type: String
Parameter Sets: ADFSFarmCreateLocalDatabaseDisableAutoCertRollover, AdfsFarmCreateLocalDatabaseDisableAutoCertRolloverGmsa, AdfsFarmCreateSharedDatabaseDisableAutoCertRolloverGmsa, ADFSFarmCreateSharedDatabaseDisableAutoCertRollover
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TlsClientPort
Specifies the port number that the AD FS service uses for Transport Layer Security (TLS) authentication for the user certificate client.
The default value is 49443.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

