---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.Deployment.Commands.dll-Help.xml
Module Name: ADCSDeployment
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/adcsdeployment/install-adcsenrollmentpolicywebservice?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Install-AdcsEnrollmentPolicyWebService
---

# Install-AdcsEnrollmentPolicyWebService

## SYNOPSIS
Performs the configuration of Certificate Enrollment Policy Web Service.

## SYNTAX

```
Install-AdcsEnrollmentPolicyWebService
 [-AuthenticationType <AuthenticationType>] [-SSLCertThumbprint <String>]
 [-KeyBasedRenewal] [-Force] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Install-AdcsEnrollmentPolicyWebService` cmdlet performs the configuration of Certificate
Enrollment Policy Web Service. It is also used to create and configure additional instances of the
service within an existing installation. To remove the certification authority (CA) role service use
the `Uninstall-AdcsEnrollmentPolicyWebService` cmdlet.

You can import the cmdlet by running the following commands from Windows PowerShell:

- `Import-Module ServerManager`
- `Add-WindowsFeature Adcs-Enroll-Web-Pol`

## EXAMPLES

### Example 1: Install the Certificate Enrollment Policy Web Service using Kerberos

```powershell
$params = @{
    AuthenticationType = Kerberos
    SSLCertThumbprint  = "a909502dd82ae41433e6f83886b00d4277a32a7b"
}
Install-AdcsEnrollmentPolicyWebService @params
```

This command installs the Certificate Enrollment Policy Web Service using Kerberos for
authentication. For information on obtaining a certificate thumbprint using Windows PowerShell, see
[Certificate Provider](https://go.microsoft.com/fwlink/?LinkId=225044).

### Example 2: Install the Certificate Enrollment Policy Web Service specifying a username and password

```powershell
$params = @{
    AuthenticationType = Username
    SSLCertThumbprint  = "a909502dd82ae41433e6f83886b00d4277a32a7b"
}
Install-AdcsEnrollmentPolicyWebService @params
```

This command installs the Certificate Enrollment Policy Web Service specifying that a username and
password is used for authentication.

### Example 3: Install the Certificate Enrollment Policy Web Service specifying a username and password for Key-Based Renewal

```powershell
$params = @{
    AuthenticationType = Username
    SSLCertThumbprint  = "a909502dd82ae41433e6f83886b00d4277a32a7b"
    KeyBasedRenewal    = $true
}
Install-AdcsEnrollmentPolicyWebService @params
```

This command installs the Certificate Enrollment Policy Web Service specifying that a username and
password is used for authentication and configures the service for Key-Based Renewal of the
certificate.

## PARAMETERS

### -AuthenticationType

Specifies the authentication type used by the Certificate Enrollment Policy Web Service.
The acceptable values for this parameter are:

- Certificate
- Kerberos
- UserName

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

Specifies the credentials for installing the Enrollment Policy Web Service. To obtain a credential
object, use the `Get-Credential` cmdlet. For more information, type `Get-Help Get-Credential`. The
Enrollment Policy Web Service must be installed on a server that is a member of an Active Directory
Domain Services (AD DS) domain. You must use an account that is a member of Domain Admins group to
install this service.

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

### -KeyBasedRenewal

Indicates that this cmdlet configures the Certificate Enrollment Policy Web Service to operate in
key-based renewal mode. Key-based renewal allows certificate clients to renew their certificates
using the key of their existing certificate for authentication. When in key-based renewal mode, the
service will only return certificate templates that are set for key based renewal.

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

Specifies the thumbprint of the certificate used by Internet Information Service (IIS) to enable
support for required Secure Sockets Layer/Transport Layer Security (SSL/TLS).

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.CertificateServices.Deployment.Common.AuthenticationType

### System.String

### System.Management.Automation.SwitchParameter

### System.Management.Automation.PSCredential

## OUTPUTS

### Microsoft.CertificateServices.Deployment.Common.CEP.EnrollmentPolicyServiceResult

## NOTES

- Ensure you run Windows PowerShell as an administrator. You can use the **Force** parameter to
  bypass the prompt for confirmation. To see parameters, run the following command:
    `Install-AdcsEnrollmentPolicyWebService -?`

- You can get the CA configuration, which is the computer name and CA name by running certutil
  without any parameters. You can see the certificate SSL certificate thumbprints assigned to the
  local computer by running the following commands:
  - `cd cert:\LocalMachine\My`
  - `dir | format-list`

## RELATED LINKS

[Uninstall-AdcsEnrollmentPolicyWebService](./Uninstall-AdcsEnrollmentPolicyWebService.md)
