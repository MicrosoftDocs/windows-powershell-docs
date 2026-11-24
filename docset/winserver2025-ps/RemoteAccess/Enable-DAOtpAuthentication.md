---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DAOtpAuthentication_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/enable-daotpauthentication?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-DAOtpAuthentication
---

# Enable-DAOtpAuthentication

## SYNOPSIS
Enables and configures one-time password (OTP) authentication for DirectAccess (DA) users.

## SYNTAX

```
Enable-DAOtpAuthentication [-RadiusServer <String>] [-ComputerName <String>] [-RadiusPort <UInt16>]
 [-CAServer <String[]>] [-CertificateTemplateName <String>] [-SharedSecret <String>]
 [-UserSecurityGroupName <String>] [-Force] [-PassThru] [-SigningCertificateTemplateName <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-DAOtpAuthentication** cmdlet enables one-time password (OTP) authentication for DirectAccess (DA) users, and configures OTP settings.

## EXAMPLES

### Example 1
```
PS C:\>Enable-DAOtpAuthentication -RadiusServer rsa.corp.contoso.com -SharedSecret abcd123$ -CAServers dc1.corp.contoso.com\corp-DC1-CA -CertificateTemplateName DAOTPLogon -PassThru -Force
OtpStatus               : Enabled
CAServers               : {dc1.corp.contoso.com\corp-DC1-CA}
CertificateTemplateName : DAOTPLogon
RadiusServer            : {rsa.corp.contoso.com}
UserSecuriotyGroupName  :

If the **Force** parameter is not used, then the DA administrator is presented with the following prompt.
PS C:\>Enable-DAOtpAuthentication -RadiusServer rsa.corp.contoso.com -SharedSecret abcd123$ -CAServers dc1.corp.contoso.com\corp-DC1-CA -CertificateTemplateName DAOTPLogon -PassThru
OtpStatus               : Enabled
CAServers               : {dc1.corp.contoso.com\corp-DC1-CA}
CertificateTemplateName : DAOTPLogon
RadiusServer            : {rsa.corp.contoso.com}
UserSecuriotyGroupName  :

Enabling OTP authentication will change DirectAccess user authentication settings. Do you want to continue?
[Y] Yes  [N] No  [S] Suspend  [?] Help  (default is "Y"):
```

This example enables OTP authentication for DA users while setting the following.

 -- rsa.corp.contoso.com as RADIUS or OTP server used to verify users OTP credentials.

 -- dc1.corp.contoso.com\corp-DC1-CA as CA server used to enroll smart card logon short lived certificates.

 -- DAOTPLogon as enroll smart card logon short lived certificates template.

All of the above settings should be set up in advance before the DA administrator can configure OTP for DA.
UserSecurityGroupName is an optional setting and thus was not set which means that the two-factor authentication exemption feature is Disabled.

This cmdlet can add one new OTP Radius server each time it runs, for additional handling of Radius servers for OTP please use RemoteAccessRadius cmdlets.
Note: This cmdlet will enable OTP if two-factor user authentication and computer certificates were already enabled using the Set-DAServer cmdlet.
If PKI and two-factor user authentication are disabled, then this cmdlet fails.
In addition enabling OTP authentication does not disable smart card or any other two-factor authentication available to the DA user.

### Example 2
```
PS C:\>Enable-DAOtpAuthentication -CertificateTemplateName DAOTPLogon_v2 -PassThru -Force
OtpStatus               : Enabled
CAServers               : {dc1.corp.contoso.com\corp-DC1-CA}
CertificateTemplateName : DAOTPLogon_v2
RadiusServer            : {rsa.corp.contoso.com}
UserSecuriotyGroupName  :
```

This example enables OTP authentication for DA users while keeping the OTP settings for RadiusServer and CAServers that were set before OTP authentication was disabled.
The CertificateTemplateName setting was updated to the new value.

The new smart card logon short lived certificates template should be created before running this cmdlet.

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
Specifies the certification authority (CA) servers that issue certificates for OTP authentication.
Specify a server in the following format:

 -- `CAServer_Name\CAService_Name`.

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
Specifies the name of the certificate template used for OTP certificate enrollment.

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

### -RadiusPort
Specifies the RADIUS server port listening for authentication requests.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: Port

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RadiusServer
Specifies the IPv4 or IPv6 address, or the fully qualified domain name (FQDN), of the RADIUS server used for OTP authentication.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Server

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SharedSecret
Specifies the shared password used for communications between the Remote Access server and the RADIUS server.

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
Specifies the security group containing users who are exempt from two-factor authentication.

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

### System.String

### System.UInt16

### System.String[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#DAOtpAuthentication

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The object contains the following OTP authentication configuration settings:

 -- OtpStatus specifies whether OTP authentication is enabled or disabled.

 -- RadiusServer specifies OTP RADIUS server names and addresses.

 -- UserSecurityGroupName specifies security group of users exempt from two-factor authentication.

 -- CAServer specifies the CA servers used for OTP authentication.

 -- CertificateTemplateName specifies the name of the OTP certificate template.

 -- SigningCertificateTemplateName specifies the name of the certificate template used to enroll the certificate used by Remote Access to sign certificates used for OTP authentication.

## NOTES

## RELATED LINKS

[Add-RemoteAccessRadius](./Add-RemoteAccessRadius.md)

[Get-RemoteAccessRadius](./Get-RemoteAccessRadius.md)

[Remove-RemoteAccessRadius](./Remove-RemoteAccessRadius.md)

[Set-DAServer](./Set-DAServer.md)

[Set-RemoteAccessRadius](./Set-RemoteAccessRadius.md)

