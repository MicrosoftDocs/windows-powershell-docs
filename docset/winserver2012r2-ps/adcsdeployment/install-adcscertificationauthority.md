---
external help file: Microsoft.CertificateServices.Deployment.Commands.dll-Help.xml
Module Name: ADCSDeployment
online version: 
schema: 2.0.0
title: Install-AdcsCertificationAuthority
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: DDC9BA9F-B2B7-47AA-A5C8-4E7E4DFE189E
---

# Install-AdcsCertificationAuthority

## SYNOPSIS
Performs installation and configuration of the Active Directory Certificate Services (AD CS) Certification Authority (CA) role service.

## SYNTAX

### NewKeyParameterSet (Default)
```
Install-AdcsCertificationAuthority [-AllowAdministratorInteraction] [-ValidityPeriod <ValidityPeriod>]
 [-ValidityPeriodUnits <Int32>] [-CACommonName <String>] [-CADistinguishedNameSuffix <String>]
 [-CAType <CAType>] [-CryptoProviderName <String>] [-DatabaseDirectory <String>] [-HashAlgorithmName <String>]
 [-IgnoreUnicode] [-KeyLength <Int32>] [-LogDirectory <String>] [-OutputCertRequestFile <String>]
 [-OverwriteExistingCAinDS] [-OverwriteExistingKey] [-ParentCA <String>] [-OverwriteExistingDatabase]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ExistingCertificateParameterSet
```
Install-AdcsCertificationAuthority [-AllowAdministratorInteraction] [-CertFilePassword <SecureString>]
 [-CertFile <String>] [-CAType <CAType>] [-CertificateID <String>] [-DatabaseDirectory <String>]
 [-LogDirectory <String>] [-OverwriteExistingKey] [-OverwriteExistingDatabase] [-Credential <PSCredential>]
 [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ExistingKeyParameterSet
```
Install-AdcsCertificationAuthority [-AllowAdministratorInteraction] [-ValidityPeriod <ValidityPeriod>]
 [-ValidityPeriodUnits <Int32>] [-CADistinguishedNameSuffix <String>] [-CAType <CAType>]
 [-CryptoProviderName <String>] [-DatabaseDirectory <String>] [-HashAlgorithmName <String>] [-IgnoreUnicode]
 [-KeyContainerName <String>] [-LogDirectory <String>] [-OutputCertRequestFile <String>]
 [-OverwriteExistingCAinDS] [-ParentCA <String>] [-OverwriteExistingDatabase] [-Credential <PSCredential>]
 [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Install-AdcsCertificationAuthority cmdlet performs installation and configuration of the AD CS CA role service.
To remove the certification authority role service use the Uninstall-AdcsCertificationAuthority cmdlet.

You can import the cmdlet by running the following commands from Windows PowerShell:
`Import-Module ServerManager`
`Add-WindowsFeature Adcs-Cert-Authority`

To include the Certification Authority and Certificate Templates consoles in a CA installation, you must add `-IncludeManagementTools` to the end of the `AddWindowsFeature Adcs-Cert-Authority` command.

Int is equivalent to Int32 in the .NET Frameworkhttp://msdn.microsoft.com/en-us/library/ya5y69ds.aspx (http://msdn.microsoft.com/en-us/library/ya5y69ds.aspx).

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Install-AdcsCertificationAuthority -CAType StandaloneRootCa
```

Description

-----------

This command installs a new Standalone Root CA with default settings.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Install-AdcsCertificationAuthority -CAType EnterpriseRootCa -CryptoProviderName "ECDSA_P256#Microsoft Software Key Storage Provider" -KeyLength 256 -HashAlgorithmName SHA256
```

Description

-----------

This command installs a new Enterprise Root CA using a specific provider (ECDSA_P256 Microsoft Software Key Storage Provider), key length (256), hash algorithm (SHA 256)

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Install-AdcsCertificationAuthority -CAType EnterpriseRootCa -CryptoProviderName "RSA#Microsoft Software Key Storage Provider" -KeyLength 2048 -HashAlgorithmName SHA1 -ValidityPeriod Years -ValidityPeriodUnits 3
```

Description

-----------

This command installs a new Enterprise Root CA with the Microsoft Software Key Storage Provider using the RSA algorithm, key length (2048), hash algorithm (SHA 256), and validity period (3 years).

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>Install-AdcsCertificationAuthority -CAType EnterpriseSubordinateCa -ParentCA SERVER75.corp.contoso.com\SERVER75-CA
```

Description

-----------

This command installs a new Enterprise subordinate CA, the parent CA is SERVER75 in the CORP domain of Contoso.com

### -------------------------- EXAMPLE 5 --------------------------
```
C:\PS>Install-AdcsCertificationAuthority -CAType EnterpriseSubordinateCa -CertFile C:\Cert\SERVER80-CA.p12 -CertFilePassword (read-host "Set user password" -assecurestring)
```

Description

-----------

This command installs an Enterprise Subordinate certification authority using an existing certificate from a PFX/P12 file that is located on the local C:\Cert folder named SERVER80-CA.p12.

## PARAMETERS

### -AllowAdministratorInteraction
Specifies whether prompting is enabled when the private key is accessed.
This is not required for any of the Microsoft default providers.
For enhanced security components, such as a hardware security module (HSM), review the enhanced security component vendor documentation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CACommonName
Specifies the certification authority common name.

```yaml
Type: String
Parameter Sets: NewKeyParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CADistinguishedNameSuffix
Specifies the certification authority distinguished name suffix.

```yaml
Type: String
Parameter Sets: NewKeyParameterSet, ExistingKeyParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CAType
Specifies the type of certification authority to install.
The possible values are: EnterpriseRootCA, EnterpriseSubordinateCA, StandaloneRootCA, or StandaloneSubordinateCA.

```yaml
Type: CAType
Parameter Sets: (All)
Aliases: 
Accepted values: EnterpriseRootCA, EnterpriseSubordinateCA, StandaloneRootCA, StandaloneSubordinateCA

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertFile
Specifies the file name of certification authority PKCS #12 formatted certificate file.

```yaml
Type: String
Parameter Sets: ExistingCertificateParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertFilePassword
Specifies the password for certification authority certificate file.

```yaml
Type: SecureString
Parameter Sets: ExistingCertificateParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertificateID
Specifies the thumbprint or serial number of certification authority certificate.

```yaml
Type: String
Parameter Sets: ExistingCertificateParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
To install an enterprise certification authority, the computer must be joined to an Active Directory Domain Services (AD DS) domain and a user account that is a member of the Enterprise Admin group is required.
To install a standalone certification authority, the computer can be in a workgroup or AD DS domain.
If the computer is in a workgroup, a user account that is a member of Administrators is required.
If the computer is in an AD DS domain, a user account that is a member of Domain Admins is required.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CryptoProviderName
The name of the cryptographic service provider (CSP) or key storage provider (KSP) that is used to generate or store the private key for the CA.

```yaml
Type: String
Parameter Sets: NewKeyParameterSet, ExistingKeyParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabaseDirectory
Specifies the folder location of the certification authority database.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force


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

### -HashAlgorithmName
Specifies the signature hash algorithm used by the certification authority.

```yaml
Type: String
Parameter Sets: NewKeyParameterSet, ExistingKeyParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IgnoreUnicode
Specifies that Unicode characters are allowed in certification authority name string.

```yaml
Type: SwitchParameter
Parameter Sets: NewKeyParameterSet, ExistingKeyParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyContainerName
Specifies the name of an existing private key container.

```yaml
Type: String
Parameter Sets: ExistingKeyParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyLength
Specifies the bit length for new certification authority key.

```yaml
Type: Int32
Parameter Sets: NewKeyParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LogDirectory
Specifies the folder location of the certification authority database log.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OutputCertRequestFile
Specifies the folder location for certificate request file.

```yaml
Type: String
Parameter Sets: NewKeyParameterSet, ExistingKeyParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OverwriteExistingCAinDS
Specifies that the computer object in the Active Directory Domain Service domain should be overwritten with the same computer name.

```yaml
Type: SwitchParameter
Parameter Sets: NewKeyParameterSet, ExistingKeyParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OverwriteExistingDatabase
Specifies that the existing certification authority database should be overwritten.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OverwriteExistingKey
Overwrite existing key container with the same name

```yaml
Type: SwitchParameter
Parameter Sets: NewKeyParameterSet, ExistingCertificateParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ParentCA
Specifies the configuration string of the parent certification authority that will certify this CA.

```yaml
Type: String
Parameter Sets: NewKeyParameterSet, ExistingKeyParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ValidityPeriod
Specifies the validity period of the certification authority (CA) certificate in hours, days, weeks, months or years. 
If this is a subordinate CA, do not use this parameter, because the validity period is determined by the parent CA.

```yaml
Type: ValidityPeriod
Parameter Sets: NewKeyParameterSet, ExistingKeyParameterSet
Aliases: 
Accepted values: Hours, Days, Weeks, Months, Years

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ValidityPeriodUnits
Validity period of the certification authority (CA) certificate. 
If this is a subordinate CA, do not specify this parameter because the validity period is determined by the parent CA.

```yaml
Type: Int32
Parameter Sets: NewKeyParameterSet, ExistingKeyParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### bool, string, string, enum, string, SecureString, string, string, string, string, bool, string, long, string, string, bool, bool, bool, string, enum, long

## OUTPUTS

### Microsoft.CertificateServices.Deployment.Commands.CA.CertificationAuthoritySetupResult

## NOTES
* Ensure you run Windows PowerShell as an administrator. You can use the -f switch to bypass the prompt for confirmation.
To see parameters, run the following command: Install-AdcsCertificationAuthority -?
If you have installation issues, try using the -verbose switch to get verbose output and review the information in the %windir%\cerocm.log.

## RELATED LINKS

[Uninstall-AdcsCertificationAuthority](./Uninstall-AdcsCertificationAuthority.md)

