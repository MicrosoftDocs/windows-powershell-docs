---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.Deployment.Commands.dll-Help.xml
Module Name: ADCSDeployment
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/adcsdeployment/install-adcsenrollmentwebservice?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Install-AdcsEnrollmentWebService
---

# Install-AdcsEnrollmentWebService

## SYNOPSIS
Performs the initial configuration of the Certificate Enrollment Web service.

## SYNTAX

### DefaultParameterSet (Default)

```
Install-AdcsEnrollmentWebService [-CAConfig <String>]
 [-ApplicationPoolIdentity] [-AuthenticationType <AuthenticationType>]
 [-SSLCertThumbprint <String>] [-RenewalOnly] [-AllowKeyBasedRenewal]
 [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ServiceAccountParameterSet

```
Install-AdcsEnrollmentWebService [-CAConfig <String>]
-ServiceAccountName <String> -ServiceAccountPassword <SecureString>
[-AuthenticationType <AuthenticationType>] [-SSLCertThumbprint <String>]
[-RenewalOnly] [-AllowKeyBasedRenewal] [-Force] [-Credential <PSCredential>]
[-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Install-AdcsEnrollmentWebService` cmdlet performs the configuration of the Certificate
Enrollment Web service. It is also used to create and configure additional instances of the service
within an existing installation. To remove the Certificate Enrollment Web Service role service use
the `Uninstall-AdcsEnrollmentWebService` cmdlet.

You can import the cmdlet by running the following commands from Windows PowerShell:

- `Import-Module ServerManager`
- `Add-WindowsFeature Adcs-Enroll-Web-Svc`

## EXAMPLES

### Example 1: Installs the Certificate Enrollment Web Service to use the certification authority

```powershell
$params = @{
    ApplicationPoolIdentity = $true
    CAConfig                = "CA1.contoso.com\contoso-CA1-CA"
    SSLCertThumbprint       = "a909502dd82ae41433e6f83886b00d4277a32a7b"
    AuthenticationType      = Certificate
}
Install-AdcsEnrollmentWebService @params
```

This command installs the Certificate Enrollment Web Service to use the certification authority with
a computer name of `CA1.contoso.com` and a CA common name `contoso-CA1-CA`. The identity of the
Certificate Enrollment Web Service is specified as the default application pool identity. The
authentication type is certificate based.

### Example 2: Installs the Certificate Enrollment Web Service to use the certification authority that prompts for password

```powershell
$params = @{
    CAConfig               = "APP1.corp.contoso.com\corp-APP1-CA"
    SSLCertThumbprint      = "a909502dd82ae41433e6f83886b00d4277a32a7b"
    ServiceAccountName     = "Corp\CEPAcct1"
    ServiceAccountPassword = (Read-Host "Set user password" -AsSecureString)
}
Install-AdcsEnrollmentWebService @params
```

This command installs the Certificate Enrollment Web Service to use the certification authority with
a computer name of `APP1.corp.contoso.com` and a CA common name `corp-APP1-CA`. The identity of the
Certificate Enrollment Web Service is specified as `CEPAcct1` from the `Corp` domain. The command
will prompt for the user password.

## PARAMETERS

### -AllowKeyBasedRenewal

Indicates that the cmdlet accepts key based renewal requests for the enrollment server, which are
valid client certificates for authentication that do not directly map to a security principal.

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

Indicates that the cmdlet configures the Certificate Enrollment Web Service to use the application
pool identity when communicating with the Certification Authority (CA). This parameter is only valid
when Certificate Enrollment Web Service targets a remote CA. If not specified, the local application
pool identity is used. This parameter is only valid when installing the first instance of the
Certificate Enrollment Web Service. If this installation will be for an additional instance of
Certificate Enrollment Web Service on this server, then this parameter should not be specified.

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

### -CAConfig

Specifies the configuration string of the CA used by the Certificate Enrollment Web Service to
process enrollment requests. This parameter depends upon whether a local CA is installed. If the CA
is local, then the parameter is optional and defaults to the local CA when not specified. If there
is not a local CA, then the parameter is required. The input of the configuration string is
`<CAComputerName>\<CACommonName>`. Replace the computer name of the (CA) for `<CAComputerName>` and
replace the CA common name for `<CACommonName>`.

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

Specifies the credentials for installing the Certificate Enrollment Web Service. To obtain a
credential object, use the `Get-Credential` cmdlet. For more information, type
`Get-Help Get-Credential`. The Certificate Enrollment Web Service must be installed on a server that
is a member of an Active Directory Domain Services (AD DS) domain. If the Certificate Enrollment Web
Service is configured to use a Standalone certification authority (CA), then an account that is a
member of the local Administrators on the CA is required. If the Enrollment Web Service is installed
to use an Enterprise CA, then using an account that is a member of Domain Admins group is required.

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

### -RenewalOnly

Indicates that the cmdlet enables renewal only mode.

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

Specifies the hash or thumbprint of the Secure Sockets Layer/Transport Layer Security (SSL/TLS)
certificate for a web site as a string value. This parameter is optional. If used, it establishes
the necessary binding with Internet Information Server (IIS) to enable support for the required
SSL/TLS connectivity. If a binding already exists within IIS, specifying this parameter overwrites
the existing binding. If this parameter is not specified, any existing binding is used. If no
bindings exist, installation succeeds, but the service will not function until the binding is
established manually.

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

Specifies the domain account for use with the service. The input string should be in the form of
`<domain>\<accountname>`. For instance, to specify an account named `WebEnroll` in the
`Corp.contoso.com` domain, you would type `CORP\WebEnroll`.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Security.SecureString

### System.Management.Automation.SwitchParameter

### Microsoft.CertificateServices.Deployment.Common.AuthenticationType

### System.Management.Automation.PSCredential

## OUTPUTS

### Microsoft.CertificateServices.Deployment.Common.CES.EnrollmentServiceResult

## NOTES

- Ensure you run Windows PowerShell as an administrator. You can use the **Force** parameter to
  bypass the prompt for confirmation. To see parameters, run the following command:
    `Install-AdcsEnrollmentWebService cmdlet -?`
- You can get the CA configuration, which is the computer name and CA name by running certutil
  without any parameters. You can see the SSL certificate thumbprints assigned to the local computer
  by running the following commands:
  - `cd cert:\LocalMachine\My`
  - `dir | format-list`

## RELATED LINKS

[Uninstall-AdcsEnrollmentWebService](./Uninstall-AdcsEnrollmentWebService.md)

[Get-Credential](https://go.microsoft.com/fwlink/?LinkID=293936)
