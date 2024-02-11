---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_RemoteAccessRADIUS_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/add-remoteaccessradius?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-RemoteAccessRadius
---

# Add-RemoteAccessRadius

## SYNOPSIS
Adds a new external RADIUS server for VPN authentication, accounting for DirectAccess (DA) and VPN, or one-time password (OTP) authentication for DA.

## SYNTAX

```
Add-RemoteAccessRadius [-ServerName] <String> [-SharedSecret] <String> [-ComputerName <String>]
 [-Port <UInt16>] [-Score <Byte>] [-Timeout <UInt32>] [-Purpose] <String> [-AccountingOnOffMsg <String>]
 [-MsgAuthenticator <String>] [-EntrypointName <String>] [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-RemoteAccessRadius** cmdlet adds a new external RADIUS server for one of the following purposes:

 -- Accounting Radius configuration applies to both DirectAccess (DA) and VPN.

 -- One-time password (OTP) RADIUS configuration applies only to DA.

 -- Authentication Radius configuration applies only to VPN.

Radius server configuration for Accounting and OTP are global in nature, such as the configurations apply to the entire Remote Access deployment.
RADIUS server configuration for VPN applies only to a specific VPN server, and all servers in a load balancing cluster, or if multi-site is deployed, to all VPN servers at a site.

Following describes aspects of this cmdlet behavior.

 -- If a RADIUS server is currently being used for a specific purpose, then it can be added for additional purpose using this cmdlet.

 -- The RADIUS server properties for authentication and accounting are the same except for the **AccountingOnOffMsg** parameter which is applicable only to accounting RADIUS and the **MsgAuthenticator** parameter which is applicable only to authentication RADIUS.
These properties are not relevant for DA OTP authentication.

 -- If a user tries to add a RADIUS server for a particular purpose but specifies a parameter that is not applicable to that purpose, then this cmdlet will still run but the parameter will be ignored and a warning message will be issued.
When adding a RADIUS server for OTP authentication both the above described parameters are ignored if specified.

 -- If the accounting configuration is Windows Server® 2012 accounting, then a user can switch to external RADIUS accounting by adding an external RADIUS server for the purpose of accounting.

 -- Following are some pre-requisites for adding a RADIUS server.

 ---- A RADIUS server cannot be added for authentication when VPN is not even installed.

 ---- A RADIUS server cannot be added for authentication when the authentication type is Windows or when local NPS is installed.

 ---- A RADIUS server cannot be added for the purpose of accounting when external RADIUS accounting is not enabled.

 ---- A RADIUS server cannot be added for purpose of OTP authentication if OTP authentication is not enabled.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Add-RemoteAccessRadius -ServerName 10.1.2.1 Authentication "s3cr3t2" -PassThru
ServerName   Purpose         Score  Timeout(s)  Port   AccountingOnOffMsg MsgAuthenticator
----------   -------         -----  ----------  ----   ------------------ ----------------
10.1.2.1     Authentication  30     5           1812                      Disabled
```

This example adds the RADIUS server named 10.1.2.1 for the purpose of VPN authentication.

### EXAMPLE 2
```
PS C:\>Add-RemoteAccessRadius -ServerName 10.1.3.1 Accounting "s3cr3t5" -PassThru
ServerName   Purpose         Score  Timeout(s)  Port   AccountingOnOffMsg MsgAuthenticator
----------   -------         -----  ----------  ----   ------------------ ----------------
10.1.3.1     Accounting      30     5           1813   Disabled
```

This example adds the RADIUS server named 10.1.3.1 for the purpose of accounting for DA and VPN.

## PARAMETERS

### -AccountingOnOffMsg
Indicates the enabled state for sending of accounting on or off messages.
The acceptable values for this parameter are:

 -- Enabled.

 -- Disabled.
This is the default value.
This parameter is applicable only when the RADIUS server is being added for Remote Access accounting.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled,

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the remote access server computer-specific tasks should be executed.
If this parameter is specified when adding a RADIUS server for authentication, then it is added for the VPN server represented by this parameter value.

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

### -EntrypointName
Specifies the identity of a site in a multi-site deployment.
This parameter is applicable only to RADIUS server configuration for VPN authentication.
It is not applicable to RADIUS accounting and OTP and hence is ignored when a user tries to add a radius server for these purposes.

When this parameter is specified it indicates that the RADIUS server for VPN authentication should be added for that site.

If this parameter is not specified in a multi-site deployment, then this parameter value for the server on which the cmdlet is run is used.
The server could also be represented by using the **ComputerName** parameter.

If this parameter and **ComputerName** parameter are specified and the **ComputerName** parameter value does not belong to the site represented by this parameter value, then this parameter takes precedence and the RADIUS server is added to it.

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

### -MsgAuthenticator
Specifies the enabled state for the usage of message authenticator.
The acceptable values for this parameter are:

 -- Enabled.

 -- Disabled.
This is the default value.

This parameter is applicable only when the RADIUS server is being added for VPN authentication.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled,

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Port
Specifies the port number on which the RADIUS server is accepting authentication requests.
The default value is `1813`.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Purpose
Specifies the purpose for which the external RADIUS server is being added.
The acceptable values for this parameter are:

 -- Authentication.

 -- Accounting.

 -- Otp.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Authentication, Accounting, Otp

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Score
Specifies the initial score.
The default value is 30.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerName
Specifies the IPv4 or IPv6 address, or host name, of the external RADIUS server.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SharedSecret
Specifies the shared secret between the VPN server and the specified external RADIUS server.
Note: The secret is specified in clear text.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
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

### -Timeout
Specifies the timeout value in seconds.
The default value is 5 (seconds).

```yaml
Type: UInt32
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

### System.Byte

### System.UInt32

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance[]

### Microsoft.Management.Infrastructure.CimInstance#RemoteAccessRadiusServer

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The RemoteAccessRadiusServer object array consists of the following properties:

 -- IPv4 or IPv6 address, or host name, of the RADIUS server that was added.

 -- The **Purpose for which the server was added** property: the RADIUS server can be added for VPN authentication, accounting or OTP.

 -- Radius initial score.

 -- Radius timeout in seconds.

 -- Radius port number.

 -- For added security, the **Radius shared secret** property is never populated; it will always show as blank.

 -- The **Status of accounting on and off messages** property is always blank if the RADIUS server was added for authentication or OTP.

 -- The **Status of message authenticator property** is always blank if the RADIUS server was added for accounting or OTP.

## NOTES

## RELATED LINKS

[Get-RemoteAccessRadius](./Get-RemoteAccessRadius.md)

[Remove-RemoteAccessRadius](./Remove-RemoteAccessRadius.md)

[Set-RemoteAccessRadius](./Set-RemoteAccessRadius.md)

