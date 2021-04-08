---
author: Kateyanne
external help file: Microsoft.CertificateServices.Deployment.Commands.dll-Help.xml
manager: dansimp
Module Name: adcsdeployment
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/adcsdeployment/install-adcsenrollmentpolicywebservice?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Install-AdcsEnrollmentPolicyWebService

## SYNOPSIS
Performs the configuration of Certificate Enrollment Policy Web service.

## SYNTAX

```
Install-AdcsEnrollmentPolicyWebService [-AuthenticationType <AuthenticationType>] [-SSLCertThumbprint <String>]
 [-KeyBasedRenewal] [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Install-AdcsEnrollmentPolicyWebService cmdlet performs the configuration of Certificate Enrollment Policy Web service.
It is also used to create additional instances of the service within an existing installation.
To remove the certification authority role service use the Uninstall-AdcsEnrollmentPolicyWebService cmdlet.

You can import the cmdlet by running the following commands from Windows PowerShell:
`Import-Module ServerManager`
`Add-WindowsFeature Adcs-Enroll-Web-Pol`

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Install-AdcsEnrollmentPolicyWebService -AuthenticationType Kerberos -SSLCertThumbprint <sslCertThumbPrint>
```

Description

-----------

This command installs the Certificate Enrollment Policy Web Service using Kerberos for authentication.
Replace \<sslCertThumbPrint\> with the actual certificate thumbprint.
For information on obtaining a certificate thumbprint using PowerShell, see Certificate Provider (http://go.microsoft.com/fwlink/?LinkId=225044).

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Install-AdcsEnrollmentPolicyWebService -AuthenticationType Username -SSLCertThumbprint <sslCertThumbPrint>
```

Description

-----------

This command installs the Certificate Enrollment Policy Web Service specifying that username and password is used for authentication.
Replace \<sslCertThumbPrint\> with the actual certificate thumbprint.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Install-AdcsEnrollmentPolicyWebService -AuthenticationType Username -SSLCertThumbprint <sslCertThumbPrint> -KeyBasedRenewal
```

Description

-----------

This command installs the Certificate Enrollment Policy Web Service specifying that username and password is used for authentication and configures the service for Key-Based Renewal of the certificate.
Replace \<sslCertThumbPrint\> with the actual certificate thumbprint.

## PARAMETERS

### -AuthenticationType
Defines the authentication type used by the Certificate Enrollment Policy Web Service: Certificate, Kerberos, or UserName.

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
Specifies the credentials for installing the Enrollment Policy Web Service.
The Enrollment Policy Web Service must be installed on a server that is a member of an Active Directory Domain Services (AD DS) domain.
You must use an account that is a member of Domain Admins group to install this service.

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

### -KeyBasedRenewal
Configures the Certificate Enrollment Policy Web Service to operate in key-based renewal mode.
Key-based renewal allows certificate clients to renew their certificates using the key of their existing certificate for authentication.
When in key-based renewal mode, the service will only return certificate templates that are set for key based renewal.

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
Specifies the thumbprint of the certificate used by Internet Information Service (IIS) to enable support for required Secure Sockets Layer (SSL).

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### enum, string, bool, PSCredential

## OUTPUTS

### Microsoft.CertificateServices.Deployment.Commands.CEP.EnrollmentPolicyServiceResult

## NOTES
* Ensure you run Windows PowerShell as an administrator. You can use the -force switch to bypass the prompt for confirmation.

  To see parameters, run the following command: install-AdcsEnrollmentPolicyWebService -?

* You can get the CA configuration, which is the computer name and CA name by running certutil without any parameters. You can see the certificate SSL certificate thumbprints assigned to the local computer by running the following commands:
`cd cert:\LocalMachine\My`
`dir | format-list`

## RELATED LINKS

[Uninstall-AdcsEnrollmentPolicyWebService](./Uninstall-AdcsEnrollmentPolicyWebService.md)

