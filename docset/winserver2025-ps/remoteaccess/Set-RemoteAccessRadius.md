---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_RemoteAccessRADIUS_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/set-remoteaccessradius?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-RemoteAccessRadius
---

# Set-RemoteAccessRadius

## SYNOPSIS
Edits the properties associated with an external RADIUS server being used for VPN authentication, accounting for DirectAccess (DA) and VPN, and one-time password (OTP) authentication for DA.

## SYNTAX

```
Set-RemoteAccessRadius [-ComputerName <String>] [-Purpose] <String> [-Port <UInt16>] [-Score <Byte>]
 [-ServerName] <String> [-Timeout <UInt32>] [-SharedSecret <String>] [-AccountingOnOffMsg <String>]
 [-MsgAuthenticator <String>] [-EntrypointName <String>] [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-RemoteAccessRadius** cmdlet edits the properties associated with an external RADIUS server being used for VPN authentication, accounting for DirectAccess (DA) and VPN, and one-time password (OTP) authentication for DA.

 -- Accounting RADIUS configuration applies to both DA and VPN.

 -- OTP RADIUS configuration applies only to DA.

 -- Authentication RADIUS configuration applies only to VPN.

A RADIUS server configuration for Accounting and OTP are global in nature, such as applying the entire Remote Access (RA) deployment.
A RADIUS server configuration for VPN applies only to a specific VPN server, and all servers in a load balancing cluster, or if multi-site is deployed, to all VPN servers at a site.

Following describes aspects of the cmdlet behavior:

 -- The purpose for which a RADIUS server is currently being used cannot be changed using this cmdlet.
Only the other properties of the server can be modified.

 -- The RADIUS server properties for authentication and accounting are the same except for the **AccountingOnOffMsg** parameter which is applicable only to accounting RADIUS and the **MsgAuthenticator** parameter which is applicable only to RADIUS authentication.
These parameters are not relevant for DA OTP authentication.

 -- If a user tries to edit the properties of a RADIUS server for a particular purpose but specifies a parameter that is not applicable to that purpose, then this cmdlet will still run but the parameter will be ignored and a warning message will be displayed.
The other parameters specified will still be modified.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-RemoteAccessRadius -ServerName 10.1.2.1 -Purpose Authentication -Timeout 10 -SharedSecret "n3ws3cr3t" -PassThru
ServerName    Purpose         Score   Timeout(s)   Port   AccountingOnOffMsg MsgAuthenticator
----------    -------         -----   ----------   ----   ------------------ ----------------
10.1.2.1      Authentication  30       10          1812                      Disabled
```

This example configures time out and shared secret properties of the RADIUS server named 10.1.2.1 that is being used for the purpose of VPN authentication.

## PARAMETERS

### -AccountingOnOffMsg
Specifies the enabled state for sending of accounting on and off messages.
The acceptable values for this parameter are:

 -- Enabled.

 -- Disabled.

This parameter is applicable only when the RADIUS server is being added for RA accounting.

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
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the RA server computer specific tasks should be run.

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
Specifies a site in a multi-site deployment.
This parameter is applicable only to RADIUS server configuration for VPN authentication.
This parameter is not applicable to RADIUS accounting and OTP.

If this parameter is specified when editing, then it indicates that the properties of the RADIUS server for VPN authentication should be modified for that site.

If an entry point is not specified in a multi-site deployment, then the entry point to which the server on which the cmdlet is run belongs is used.
The server could also be represented by using the **ComputerName** parameter.

If this parameter and the **ComputerName** parameter are specified and the **ComputerName** parameter does not belong to the site represented by this parameter, then this parameter takes precedence and the RADIUS server is added to it.

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
Specifies the purpose of the RADIUS server for which the settings are being modified.
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
Specifies the IPv4 or IPv6 address, or host name, of the external RADIUS server for which the properties are being modified for the specified purpose.

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
Note: The secret is specified in plain text.

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

### -Timeout
Specifies the time-out value, in seconds.

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

The array of RemoteAccessRadiusServer objects consists of the following properties:

 -- The IPv4 or IPv6 address or host name of the RADIUS server that was modified.

 -- The purpose for which the server was modified: VPN authentication, accounting or OTP.

 -- The RADIUS initial score.

 -- The RADIUS timeout in seconds.

 -- The RADIUS port number.

 -- The RADIUS shared secret: for security reasons, this property is never populated and will always show as blank.

 -- The status of accounting on/off messages: if the RADIUS server was modified for authentication or OTP, then this property is always blank.

 -- The status of message authenticator: if the RADIUS server was modified for accounting or OTP, then this property is always blank.

## NOTES

## RELATED LINKS

[Add-RemoteAccessRadius](./Add-RemoteAccessRadius.md)

[Get-RemoteAccessRadius](./Get-RemoteAccessRadius.md)

[Remove-RemoteAccessRadius](./Remove-RemoteAccessRadius.md)

[Set-RemoteAccessRadius](./Set-RemoteAccessRadius.md)

