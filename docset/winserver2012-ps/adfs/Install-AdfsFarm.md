---
external help file: Microsoft.FederationServices.Deployment.dll-Help.xml
Module Name: ADFS
online version: https://docs.microsoft.com/powershell/module/adfs/install-adfsfarm?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Install-AdfsFarm

## SYNOPSIS
Creates the first node of a new federation server farm.

## SYNTAX

### ADFSFarmCreateDefault (Default)
```
Install-AdfsFarm -CertificateThumbprint <String> -FederationServiceName <String> [-OverwriteConfiguration]
 -ServiceAccountCredential <PSCredential> [-SSLPort <Int32>] [<CommonParameters>]
```

### ADFSFarmCreateSQL
```
Install-AdfsFarm -CertificateThumbprint <String> -FederationServiceName <String> [-OverwriteConfiguration]
 -ServiceAccountCredential <PSCredential> -SQLConnectionString <String> [-SSLPort <Int32>] [<CommonParameters>]
```

### ADFSFarmCreateDisableAutoCertRollover
```
Install-AdfsFarm -CertificateThumbprint <String> -DecryptionCertificateThumbprint <String>
 -FederationServiceName <String> [-OverwriteConfiguration] -ServiceAccountCredential <PSCredential>
 -SigningCertificateThumbprint <String> [-SSLPort <Int32>] [<CommonParameters>]
```

### ADFSFarmCreateSQLDisableAutoCertRollover
```
Install-AdfsFarm -CertificateThumbprint <String> -DecryptionCertificateThumbprint <String>
 -FederationServiceName <String> [-OverwriteConfiguration] -ServiceAccountCredential <PSCredential>
 -SigningCertificateThumbprint <String> -SQLConnectionString <String> [-SSLPort <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The Install-Adfsfarm cmdlet creates the first node of a new federation server farm.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>$fscredential = Get-Credential
C:\PS>Install-AdfsFarm -CertificateThumbprint 8169c52b4ec6e77eb2ae17f028fe5da4e35c0bed -FederationServiceName fs.corp.contoso.com -ServiceAccountCredential $fscredential
```

Description

-----------

Creates the first node in a federation server farm that uses the Windows Internal Database (WID) on the local server computer.

In this example, a certificate thumbprint value is supplied for the CertificateThumbprint parameter. 
This certificate will be used as the SSL certificate and the service communications certificate. 
Automatically generated, self signed certificates will be used for the token signing and token decryption certificates.

To specify certificates for token signing and token decryption, specify thumbprint values for the SigningCertificateThumbprint and DecryptionCertificateThumbprint parameters.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>dir cert:\LocalMachine\My
```

Description

-----------

Lists thumbprint values of currently installed certificates.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>$fscredential = Get-Credential
C:\PS>Install-AdfsFarm -CertificateThumbprint 8169c52b4ec6e77eb2ae17f028fe5da4e35c0bed -FederationServiceName fs.corp.contoso.com -ServiceAccountCredential $fscredential -SQLConnectionString "Data Source=SQLHost;Integrated Security=True"
```

Description

-----------

Creates the first node in a federation server farm that uses a Microsoft SQL server database on a remote computer named "SQLHost".

In this example, a certificate thumbprint value is supplied for the CertificateThumbprint parameter. 
This certificate will be used as the SSL certificate and the service communications certificate. 
Automatically generated, self signed certificates will be used for the token signing and token decryption certificates.

To specify certificates for token signing and token decryption, specify thumbprint values for the SigningCertificateThumbprint and DecryptionCertificateThumbprint parameters.

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>$fscredential = Get-Credential
C:\PS>Install-AdfsFarm -CertificateThumbprint 8169c52b4ec6e77eb2ae17f028fe5da4e35c0bed -FederationServiceName fs.corp.contoso.com -ServiceAccountCredential $fscredential -SQLConnectionString "Data Source=SQLHost;Integrated Security=True" -OverwriteConfiguration -SigningCertificateThumbprint 8169c52b4ec6e77eb2ae17f028fe5da4e35c0bed -DecryptionCertificateThumbprint cf2e5064c521d625c8d53536bc98aa8e08f5f2ad
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

Required: True
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
Parameter Sets: ADFSFarmCreateDisableAutoCertRollover, ADFSFarmCreateSQLDisableAutoCertRollover
Aliases: 

Required: True
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

### -OverwriteConfiguration
This parameter must be used to remove an existing AD FS configuration database and overwrite it with a new database.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -SQLConnectionString
Specifies the SQL Server database that will store the AD FS configuration settings. 
If not specified, the AD FS installer uses the Windows Internal Database to store configuration settings.

```yaml
Type: String
Parameter Sets: ADFSFarmCreateSQL, ADFSFarmCreateSQLDisableAutoCertRollover
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
Default value: 443
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceAccountCredential
Specifies the Active Directory account under which the AD FS service runs.

```yaml
Type: PSCredential
Parameter Sets: (All)
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
Parameter Sets: ADFSFarmCreateDisableAutoCertRollover, ADFSFarmCreateSQLDisableAutoCertRollover
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### none

## OUTPUTS

### Result object

## NOTES

## RELATED LINKS

