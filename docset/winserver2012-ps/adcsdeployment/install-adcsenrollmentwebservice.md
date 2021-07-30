---
external help file: Microsoft.CertificateServices.Deployment.Commands.dll-Help.xml
Module Name: adcsdeployment
online version: https://docs.microsoft.com/powershell/module/adcsdeployment/install-adcsenrollmentwebservice?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Install-AdcsEnrollmentWebService

## SYNOPSIS
Performs initial configuration of the Certificate Enrollment Web service.

## SYNTAX

### DefaultParameterSet (Default)
```
Install-AdcsEnrollmentWebService [-CAConfig <String>] [-ApplicationPoolIdentity]
 [-AuthenticationType <AuthenticationType>] [-SSLCertThumbprint <String>] [-RenewalOnly]
 [-AllowKeyBasedRenewal] [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ServiceAccountParameterSet
```
Install-AdcsEnrollmentWebService [-CAConfig <String>] -ServiceAccountName <String>
 -ServiceAccountPassword <SecureString> [-AuthenticationType <AuthenticationType>]
 [-SSLCertThumbprint <String>] [-RenewalOnly] [-AllowKeyBasedRenewal] [-Force] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Install-AdcsEnrollmentWebService cmdlet performs the configuration of Certificate Enrollment Web service.
It is also used to create additional instances of the service within an existing installation.
To remove the Certificate Enrollment Web Service role service use the Uninstall-AdcsEnrollmentWebService cmdlet.

You can import the cmdlet by running the following commands from Windows PowerShell:
`Import-Module ServerManager`
`Add-WindowsFeature Adcs-Enroll-Web-Svc`

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Install-AdcsEnrollmentWebService -ApplicationPoolIdentity -CAConfig CA1.contoso.com\contoso-CA1-CA -SSLCertThumbprint <thumbprint> -AuthenticationType Certificate
```

Description

-----------

This command installs the Certificate Enrollment Web Service to use the certification authority with a computer name of CA1.contoso.com and a CA common name contoso-CA1-CA.
The identity of the Certificate Enrollment Web Service is specified as the default application pool identity.
The placeholder \<thumbprint\> should be replaced with the actual thumbprint of the certificate associated with the service.
The authentication type is certificate based.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Install-AdcsEnrollmentWebService -CAConfig APP1.corp.contoso.com\corp-APP1-CA -SSLCertThumbprint <thumbprint> -ServiceAccountName Corp\CEPAcct1 -ServiceAccountPassword (read-host "Set user password" -assecurestring)
```

Description

-----------

This command installs the Certificate Enrollment Web Service to use the certification authority with a computer name of APP1.corp.contoso.com and a CA common name corp-APP1-CA.
The placeholder \<thumbprint\> should be replaced with the actual thumbprint of the certificate associated with the service.
The identity of the Certificate Enrollment Web Service is specified as CEPAcct1 from the Corp domain.
The command will prompt for the user password.

## PARAMETERS

### -AllowKeyBasedRenewal
Specifies that the enrollment server accept key based renewal requests, which are valid client certificate for authentication that do not directly map to a security principal.

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

### -ApplicationPoolIdentity
Specifies the identity that the Certificate Enrollment Web Service will use when communicating with the Certification Authority (CA).
This parameter is only valid when Certificate Enrollment Web Service will be targeting a remote CA.
If not specified, the local application pool identity is used.
This parameter is only valid when installing the first instance of the Certificate Enrollment Web Service.
If this installation will be for an additional instance of Certificate Enrollment Web Service on this server, then this parameter should not be specified.

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

### -AuthenticationType
Specifies the authentication type.
Valid options include: Certificate, Kerberos, and UserName.

```yaml
Type: AuthenticationType
Parameter Sets: (All)
Aliases: 
Accepted values: Kerberos, UserName, Certificate

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CAConfig
Specifies the configuration string of the Certification Authority (CA) used by the Certificate Enrollment Web Service to process enrollment requests.
This parameter depends upon whether a local CA is installed.
If the CA is local, then the parameter is optional and defaults to the local CA when not specified.
If there is not a local CA, then the parameter is required.
The input is the configuration string is \<CAComputerName\>\\\<CACommonName\>.
Replace the computer name of the (CA) for \<CAComputerName\> and replace the CA common name for \<CACommonName\>.

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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the credentials for installing the Certificate Enrollment Web Service.
The Certificate Enrollment Web Service must be installed on a server that is a member of an Active Directory Domain Services (AD DS) domain.
If the Certificate Enrollment Web Service is configured to use a Standalone certification authority (CA), then an account that is a member of the local Administrators on the CA is required.
If the Enrollment Web Service is installed to use an Enterprise CA, then using an account that is a member of Domain Admins group is required.

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

### -RenewalOnly
Specifies that renewal only mode be enabled.

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

### -SSLCertThumbprint
Specifies the hash or thumbprint of the Secure Sockets Layer/Transport Layer Security (SSL/TLS) certificate for a web site as a string value.
This parameter is optional.
If used, it will establish the necessary binding with Internet Information Server (IIS) to enable support for the required SSL/TLS connectivity.
If a binding already exists within IIS, specifying this parameter overwrites the existing binding.
If this parameter is not specified, any existing binding is used.
If no bindings exist, installation succeeds, but the service will not function until the binding is established manually.

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
Specifies the domain account for use with the service.
The input string should be in the form of \<domain\>\\\<accountname\>.
For example, to specify an account named WebEnroll in the Corp.contoso.com domain, you would type CORP\WebEnroll.

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
Specifies the password for the domain account used as the service account.

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

### bool, bool, enum, string, bool, string, SecureString, string, PSCredential

## OUTPUTS

### Microsoft.CertificateServices.Deployment.Commands.CES.EnrollmentServiceResult

## NOTES
* Ensure you run Windows PowerShell as an administrator. You can use the -force switch to bypass the prompt for confirmation.
To see parameters, run the following command: install-AdcsEnrollmentWebService cmdlet -?
* You can get the CA configuration, which is the computer name and CA name by running certutil without any parameters. You can see the SSL certificate thumbprints assigned to the local computer by running the following commands:
`cd cert:\LocalMachine\My`
`dir | format-list`

## RELATED LINKS

[Uninstall-AdcsEnrollmentWebService](./Uninstall-AdcsEnrollmentWebService.md)

