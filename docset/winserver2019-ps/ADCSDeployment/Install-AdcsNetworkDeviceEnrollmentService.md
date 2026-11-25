---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.Deployment.Commands.dll-Help.xml
Module Name: ADCSDeployment
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/adcsdeployment/install-adcsnetworkdeviceenrollmentservice?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Install-AdcsNetworkDeviceEnrollmentService
---

# Install-AdcsNetworkDeviceEnrollmentService

## SYNOPSIS
Installs the NDES role service.

## SYNTAX

### DefaultParameterSet (Default)
```
Install-AdcsNetworkDeviceEnrollmentService [-ApplicationPoolIdentity] [-RAName <String>] [-RAEmail <String>]
 [-RACompany <String>] [-RADepartment <String>] [-RACity <String>] [-RAState <String>] [-RACountry <String>]
 [-SigningProviderName <String>] [-SigningKeyLength <Int32>] [-EncryptionProviderName <String>]
 [-EncryptionKeyLength <Int32>] [-CAConfig <String>] [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ServiceAccountParameterSet
```
Install-AdcsNetworkDeviceEnrollmentService -ServiceAccountName <String> -ServiceAccountPassword <SecureString>
 [-RAName <String>] [-RAEmail <String>] [-RACompany <String>] [-RADepartment <String>] [-RACity <String>]
 [-RAState <String>] [-RACountry <String>] [-SigningProviderName <String>] [-SigningKeyLength <Int32>]
 [-EncryptionProviderName <String>] [-EncryptionKeyLength <Int32>] [-CAConfig <String>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Install-AdcsNetworkDeviceEnrollmentService** cmdlet performs the configuration of the Network Device Enrollment Service (NDES) role service.

To remove the NDES role service, use the **Uninstall-AdcsNetworkDeviceEnrollmentService** cmdlet.

You can import the cmdlet by running the following commands from Windows PowerShell:

- `Import-Module ServerManager`
- `Add-WindowsFeature Adcs-Device-Enrollment`

Int is equivalent to Int32 in the [.NET Framework](https://msdn.microsoft.com/en-us/library/ya5y69ds.aspx).

## EXAMPLES

### Example 1: Display the default NDES settings
```
PS C:\> Install-AdcsNetworkDeviceEnrollmentService -ApplicationPoolIdentity -WhatIf
```

This command displays the default NDES settings that will be configured if it is installed.

### Example 2: Display the default NDES settings using a service account name and password
```
PS C:\> Install-AdcsNetworkDeviceEnrollmentService -ServiceAccountName "CONTOSO\svcNDES" -ServiceAccountPassword (read-host "Set user password" -assecurestring) -WhatIf
```

This command displays the default settings when NDES is using a service account without making any changes to the configuration.
This command uses the service account named "CONTOSO\svcNDES" that is a member of the local computer's IIS_USRS group.

### Example 3: Install NDES using the application pool identity
```
PS C:\> Install-AdcsNetworkDeviceEnrollmentService -ApplicationPoolIdentity -CAConfig "<CAComputerName>\<CACommonName>"
```

This command installs NDES using the application pool identity to use a remote CA as specified by the CA computer `<CAComputerName>\<CACommonName>`.
Substitute the appropriate CA computer name and common name for `<CAComputerName>` and `<CACommonName>`.

### Example 4: Install NDES using a specific service account
```
PS C:\> Install-AdcsNetworkDeviceEnrollmentService -ServiceAccountName "CONTOSO\svcNDES" -ServiceAccountPassword (read-host "Set user password" -assecurestring) -CAConfig "CAComputerName\CAName" -RAName "Contoso-NDES-RA" -RACountry "US" -RACompany "Contoso" -SigningProviderName "Microsoft Strong Cryptographic Provider" -SigningKeyLength 4096 -EncryptionProviderName "Microsoft Strong Cryptographic Provider" -EncryptionKeyLength 4096
```

This command installs the NDES using a service account named "CONTOSO\svcNDES" that is a member of the local computer's IIS_USRS group.
The command also specifies several non-default parameters.

## PARAMETERS

### -ApplicationPoolIdentity
Indicates that the cmdlet the identity that the Network Device Enrollment Service (NDES) uses when communicating with the certification authority (CA).
This parameter is only valid when NDES is using a remote CA.
If the CA is local, the application pool identity account cannot be used.

```yaml
Type: SwitchParameter
Parameter Sets: DefaultParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CAConfig
Specifies remote certification authority (CA) that the Network Device Enrollment Service uses.
This parameter is mandatory when used within the *ApplicationPoolIdentity* parameter.
Do not use this parameter when a local CA is installed.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a **PSCredential** object that this cmdlet use to connect to the NDES role service.
To obtain a credential object, use the **Get-Credential** cmdlet.
For more information, type `Get-Help Get-Credential`.
The NDES must be installed on a server that is a member of an Active Directory Domain Services (AD DS) domain.
If NDES is configured to use a Standalone CA, then an account that is a member of the local Administrators on the CA is required.
If NDES is installed to use an Enterprise CA, then using an account that is a member of Domain Admins group is required.

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

### -EncryptionKeyLength
Specifies the encryption key length.
This option is not valid if you use existing keys during installation.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EncryptionProviderName
Specifies the name of the encryption provider, such as the name of cryptographic service provider (CSP).

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

### -RACity
Specifies the city of the registration authority.

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

### -RACompany
Specifies the organization or company that the registration authority represents.

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

### -RACountry
Specifies the country/region of the registration authority.

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

### -RADepartment
Specifies the department of the registration authority.

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

### -RAEmail
Specifies the email address of the registration authority.

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

### -RAName
Specifies the name of the NDES registration authority.

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

### -RAState
Specifies the state or province (geographical political boundary), if applicable, of the registration authority.

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

### -ServiceAccountName
Specifies the name of the account that is used by the Network Device Enrollment Service.

```yaml
Type: String
Parameter Sets: ServiceAccountParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceAccountPassword
Specifies the password of the service account that is used by the Network Device Enrollment Service.

```yaml
Type: SecureString
Parameter Sets: ServiceAccountParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SigningKeyLength
Specifies the signing key length.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SigningProviderName
Specifies the name of the signing device.

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

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### bool, int, string, string, string, string, string, string, string, string, string, SecurePassword, int, string

## OUTPUTS

### Microsoft.CertificateServices.Deployment.Commands.NDES.NetworkDeviceEnrollmentServiceResult

## NOTES
* Ensure you run Windows PowerShell as an administrator. You can use the *Force* parameter to bypass the prompt for confirmation.
To see parameters, run the following command: `Install-AdcsNetworkDeviceEnrollmentService -?`

  

## RELATED LINKS

[Uninstall-AdcsNetworkDeviceEnrollmentService](./Uninstall-AdcsNetworkDeviceEnrollmentService.md)

[Get-Credential](https://go.microsoft.com/fwlink/?LinkID=293936)

