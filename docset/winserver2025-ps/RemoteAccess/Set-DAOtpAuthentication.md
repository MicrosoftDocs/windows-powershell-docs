---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DAOtpAuthentication_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/set-daotpauthentication?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DAOtpAuthentication
---

# Set-DAOtpAuthentication

## SYNOPSIS
Configures one-time password (OTP) authentication settings for DirectAccess (DA).

## SYNTAX

```
Set-DAOtpAuthentication [-ComputerName <String>] [-CertificateTemplateName <String>] [-CAServer <String[]>]
 [-UserSecurityGroupName <String>] [-DisableTwoFactorBypass] [-PassThru]
 [-SigningCertificateTemplateName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DAOtpAuthentication** cmdlet modifies the DirectAccess (DA) one-time password (OTP) settings, including certification authority (CA) servers, the certificate template used to issue one-time password (OTP) certificates, and users exempt from two-factor authentication.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-DAOtpAuthentication -CAServer @(DC1.corp.contoso.com\corp-DC1-CA, DC2.corp.contoso.com\corp-DC2-CA) -PassThru
OtpStatus               : Enabled
CAServers               : {dc1.corp.contoso.com\corp-DC1-CA, dc2.corp.contoso.com\corp-DC2-CA}
CertificateTemplateName : DAOTPLogon
RadiusServer            : {rsa.corp.contoso.com}
UserSecurityGroupName   :
```

This example changes OTP setting for both DC1.corp.contoso.com\corp-DC1-CA and DC2.corp.contoso.com\corp-DC2-CA CA server to be used for OTP authentication.
Other OTP settings will not be changed in any way.
This cmdlet can be used to change single or multiple OTP settings.
Note: This cmdlet will fail if OTP authentication is Disabled.

### EXAMPLE 2
```
PS C:\>Set-DAOtpAuthentication -UserSecuriotyGroupName corp\DirectAccessUsernamePasswordUsers -PassThru
OtpStatus               : Disabled
CAServers               : {dc1.corp.contoso.com\corp-DC1-CA}
CertificateTemplateName : DAOTPLogon
RadiusServer            : {rsa.corp.contoso.com}
UserSecurityGroupName   : CORP\DirectAccessUsernamePasswordUsers
```

This example enables two-factor authentication exemption feature and sets CORP\DirectAccessUsernamePasswordUsers as security group of users who are allowed to use username and password as user authentication for DA.

The appropriate user group should be created in advance before DA admin can configure OTP for DA.
A DA administrator cannot add users to this group via the DA administrator console.

### EXAMPLE 3
```
PS C:\>Set-DAOtpAuthentication -DisableTwoFactorBypass -PassThru
OtpStatus               : Disabled
CAServers               : {dc1.corp.contoso.com\corp-DC1-CA}
CertificateTemplateName : DAOTPLogon
RadiusServer            : {rsa.corp.contoso.com}
UserSecurityGroupName   :
```

This example disables two-factor user authentication exemption feature and all DA users must use two-factor authentication such as Smart Card or OTP, as user authentication for DA.
The value of the **UserSecurityGroupName** parameter is cleared and next time two-factor authentication feature is Enabled again, the DA administrator will have to supply the name of user security group.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -CAServer
Specifies the CA servers that issue certificates for OTP authentication.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertificateTemplateName
Specifies the name of the certificate template used for OTP.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the IPv4 or IPv6 address, or host name, of the server on which the cmdlet should run.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn

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

### -DisableTwoFactorBypass
Disables the option to allow users in a specific security group to be exempt from two-factor authentication, when two-factor authentication is enabled.

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

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -SigningCertificateTemplateName
Specifies the name of the certificate template used to enroll the certificate used by Remote Access to sign certificates used for OTP authentication.

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

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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

### -UserSecurityGroupName
Specifies a security group containing users who are exempt from two-factor authentication.

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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DAOtpAuthentication

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The DAOtpAuth object contains the following OTP authentication configuration settings for DirectAccess:

 -- OtpStatus specifies whether OTP authentication is enabled or disabled.

 -- RadiusServer specifies the OTP RADIUS server names and addresses.

 -- UserSecurityGroupName specifies the security group of users that are exempt from two-factor authentication.

 -- CAServer specifies the CA servers used for OTP authentication.

 -- CertificateTemplateName specifies the name of the OTP certificate template.

 -- SigningCertificateTemplateName specifies the name of the certificate template used to enroll the certificate used by Remote Access to sign certificates used for OTP authentication.

## NOTES

## RELATED LINKS

[Disable-DAOtpAuthentication](./Disable-DAOtpAuthentication.md)

[Enable-DAOtpAuthentication](./Enable-DAOtpAuthentication.md)

[Get-DAOtpAuthentication](./Get-DAOtpAuthentication.md)

