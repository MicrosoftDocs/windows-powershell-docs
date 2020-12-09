---
external help file: UnifiedRA_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 7BEEA630-EBB9-4C83-8066-CEC3371AA1E4
manager: dansimp
---

# Get-DAOtpAuthentication

## SYNOPSIS
Displays one-time password (OTP) authentication settings for DirectAccess (DA).

## SYNTAX

```
Get-DAOtpAuthentication [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DAOtpAuthentication** cmdlet displays DirectAccess (DA) one-time password (OTP) settings, including the enabled state of the OTP, the RADIUS servers used for OTP authentication, certification authority (CA) servers, the certificate template used to issue OTP certificates, and optionally, a security group of users exempt from two-factor authentication.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DAOtpAuthentication
OtpStatus                : Enabled 
CAServers                : {dc1.corp.contoso.com\corp-DC1-CA} 
CertificateTemplateName  : DAOTPLogon 
RadiusServer             : {RSA.corp.contoso.com} 
UserSecuriotyGroupName   :
```

This example retrieves OTP authentication settings from DA Server Group Policy Object (GPO) and displays the settings to the caller.
If OTP authentication is Enabled, then the status will show Enabled.
If OTP authentication is Disabled, then the status shown will be Disabled.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DAOtpAuth
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The DAOtpAuth object contains the following OTP authentication configuration settings for DA:. 

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

[Set-DAOtpAuthentication](./Set-DAOtpAuthentication.md)

