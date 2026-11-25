---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Deployment.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/test-adfsfarminstallation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-AdfsFarmInstallation
---

# Test-AdfsFarmInstallation

## SYNOPSIS
Runs prerequisite checks for installing a new federation server farm.

## SYNTAX

### ADFSFarmCreateLocalDatabase (Default)
```
Test-AdfsFarmInstallation [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 -FederationServiceName <String> [-FederationServiceDisplayName <String>]
 -ServiceAccountCredential <PSCredential> [-OverwriteConfiguration] [-SSLPort <Int32>] [-TlsClientPort <Int32>]
 [-AdminConfiguration <Hashtable>] [<CommonParameters>]
```

### ADFSFarmCreateLocalDatabaseDisableAutoCertRollover
```
Test-AdfsFarmInstallation [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 -DecryptionCertificateThumbprint <String> -FederationServiceName <String>
 [-FederationServiceDisplayName <String>] -ServiceAccountCredential <PSCredential>
 -SigningCertificateThumbprint <String> [-OverwriteConfiguration] [-SSLPort <Int32>] [-TlsClientPort <Int32>]
 [-AdminConfiguration <Hashtable>] [<CommonParameters>]
```

### ADFSFarmCreateSharedDatabaseDisableAutoCertRollover
```
Test-AdfsFarmInstallation [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 -DecryptionCertificateThumbprint <String> -FederationServiceName <String>
 [-FederationServiceDisplayName <String>] -ServiceAccountCredential <PSCredential>
 -SigningCertificateThumbprint <String> -SQLConnectionString <String> [-OverwriteConfiguration]
 [-SSLPort <Int32>] [-TlsClientPort <Int32>] [-AdminConfiguration <Hashtable>] [<CommonParameters>]
```

### AdfsFarmCreateLocalDatabaseDisableAutoCertRolloverGmsa
```
Test-AdfsFarmInstallation [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 -DecryptionCertificateThumbprint <String> -FederationServiceName <String>
 [-FederationServiceDisplayName <String>] -GroupServiceAccountIdentifier <String>
 -SigningCertificateThumbprint <String> [-OverwriteConfiguration] [-SSLPort <Int32>] [-TlsClientPort <Int32>]
 [-AdminConfiguration <Hashtable>] [<CommonParameters>]
```

### AdfsFarmCreateSharedDatabaseDisableAutoCertRolloverGmsa
```
Test-AdfsFarmInstallation [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 -DecryptionCertificateThumbprint <String> -FederationServiceName <String>
 [-FederationServiceDisplayName <String>] -GroupServiceAccountIdentifier <String>
 -SigningCertificateThumbprint <String> -SQLConnectionString <String> [-OverwriteConfiguration]
 [-SSLPort <Int32>] [-TlsClientPort <Int32>] [-AdminConfiguration <Hashtable>] [<CommonParameters>]
```

### ADFSFarmCreateSharedDatabase
```
Test-AdfsFarmInstallation [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 -FederationServiceName <String> [-FederationServiceDisplayName <String>]
 -ServiceAccountCredential <PSCredential> -SQLConnectionString <String> [-OverwriteConfiguration]
 [-SSLPort <Int32>] [-TlsClientPort <Int32>] [-AdminConfiguration <Hashtable>] [<CommonParameters>]
```

### AdfsFarmCreateLocalDatabaseGmsa
```
Test-AdfsFarmInstallation [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 -FederationServiceName <String> [-FederationServiceDisplayName <String>]
 -GroupServiceAccountIdentifier <String> [-OverwriteConfiguration] [-SSLPort <Int32>] [-TlsClientPort <Int32>]
 [-AdminConfiguration <Hashtable>] [<CommonParameters>]
```

### AdfsFarmCreateSharedDatabaseGmsa
```
Test-AdfsFarmInstallation [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 -FederationServiceName <String> [-FederationServiceDisplayName <String>]
 -GroupServiceAccountIdentifier <String> -SQLConnectionString <String> [-OverwriteConfiguration]
 [-SSLPort <Int32>] [-TlsClientPort <Int32>] [-AdminConfiguration <Hashtable>] [<CommonParameters>]
```

## DESCRIPTION
The **Test-AdfsFarmInstallation** cmdlet performs the checks that you must complete before you run the Install-AdfsFarm cmdlet to install a new federation server farm.

## EXAMPLES

### Example 1: Test the creation of a node in a federation server farm
```
PS C:\> $Cred = Get-Credential
PS C:\> Test-AdfsFarmInstallation -CertificateThumbprint 8169c52b4ec6e77eb2ae17f028fe5da4e35c0bed -FederationServiceName "FS.Corp.Contoso.com" -ServiceAccountCredential $Cred
```

The first command uses the **Get-Credential** cmdlet to create a credential object for the Active Directory account under which the AD FS service runs.
The command stores the credential object in the $Cred variable.

The second command tests the creation the first node in a federation server farm that uses the Windows Internal Database on the local server computer.
The command specifies a thumbprint of the certificate.
AD FS uses this certificate as the SSL certificate and the service communications certificate.
The command uses automatically generated, self-signed certificates for the token signing and token decryption certificates.
The command specifies the credentials stored in $Cred for the Active Directory account under which the AD FS service runs.

## PARAMETERS

### -AdminConfiguration
Specifies admin configuration.

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
Specifies the value of the thumbprint of the certificate that the Secure Sockets Layer (SSL) binding of the default website uses in Internet Information Services (IIS).
This value must match the thumbprint of a valid certificate in the certificate store of the local computer.

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
Specifies a **PSCredential** object based on a user name and password.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type `Get-Help Get-Credential`.

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
Specifies the value of the thumbprint of the certificate that Active Directory Federation Services (AD FS) uses for token decryption.
If you specify this parameter, AD FS disables automatic certificate rollover, and you must specify a token signing certificate by specifying the **SigningCertificateThumbprint** parameter.
This value must match the thumbprint of a valid certificate in the certificate store of the local computer.

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
Specifies the display name of the Federation Service.
The name of the Federation Service appears by default in sign-in pages.

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
Specifies the Domain Name System (DNS) name of the Federation Service.
This value must match the subject name of the certificate that you configure on the SSL binding in IIS.

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
Specifies the name of the group Managed Service Account that the AD FS service uses as the logon identity for the AD FS Windows service.

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
Indicates that the AD FS service removes an existing AD FS configuration database and overwrites it with a new database.

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
Specifies a **PSCredential** object based on a user name and password for the service account in Active Directory® Domain Services under which the AD FS service runs.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type `Get-Help Get-Credential`.

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
Specifies the value of the thumbprint of the certificate that the AD FS service uses for token signing.
If you specify this parameter, AD FS disables automatic certificate rollover, and you must also specify a token decryption certificate by using the **DecryptionCertificateThumbprint** parameter.
This value must match the thumbprint of a valid certificate in the certificate store of the local computer.

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
Specifies the Microsoft SQL Server database that stores the AD FS configuration settings.
If you do not specify this parameter, the AD FS installer uses the Windows Internal Database to store configuration settings.

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
Specifies the value of the port number of the SSL binding that the AD FS website uses.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-Credential](https://go.microsoft.com/fwlink/?LinkID=293936)

[Install-AdfsFarm](./Install-AdfsFarm.md)

[Test-AdfsFarmJoin](./Test-AdfsFarmJoin.md)

