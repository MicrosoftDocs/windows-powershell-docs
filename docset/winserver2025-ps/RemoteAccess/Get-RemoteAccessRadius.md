---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_RemoteAccessRADIUS_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-remoteaccessradius?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RemoteAccessRadius
---

# Get-RemoteAccessRadius

## SYNOPSIS
Displays the list of RADIUS servers including RADIUS for VPN authentication, RADIUS for DirectAccess (DA) and VPN Accounting, and RADIUS for one-time password (OTP) authentication for DA.

## SYNTAX

```
Get-RemoteAccessRadius [[-Purpose] <String>] [-ComputerName <String>] [-EntrypointName <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RemoteAccessRadius** cmdlet displays the list of RADIUS servers including RADIUS for VPN authentication, RADIUS for DirectAccess (DA) and VPN Accounting, and RADIUS for one-time password (OTP) authentication for DA.

The following is the information displayed for each RADIUS server.
If a RADIUS server is being used for multiple purposes, then a separate entry is displayed for each purpose.

 -- Server address.

 -- Purpose that it is being used for.

 -- Initial score.

 -- Timeout, in seconds.

 -- Port.

 -- Shared secret.

 -- Status of accounting on and off messages, only if the server is being used for accounting.

 -- Status of message authenticator, only if the server is being used for VPN authentication.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-RemoteAccessRadius
ServerName      Purpose         Score   Timeout(s)  Port    AccountingOnOffMsg MsgAuthenticator
----------      -------         -----   ----------  ----    ------------------ ----------------
10.1.1.1        Accounting       30       5         1813    Disabled
10.1.3.1        Accounting       30       5         1813    Disabled
10.1.1.1        Authentication   30       5         1812                       Disabled
10.1.2.1        Authentication   30       5         1812                       Disabled


PS C:\>Remove-RemoteAccessRadius -ServerName 10.1.1.1 -Purpose Authentication -PassThru
ServerName : 10.1.1.1
Purpose    : Authentication


PS C:\>Get-RemoteAccessRadius
ServerName      Purpose         Score   Timeout(s)  Port    AccountingOnOffMsg MsgAuthenticator
----------      -------         -----   ----------  ----    ------------------ ----------------
10.1.1.1        Accounting       30       5         1813    Disabled
10.1.3.1        Accounting       30       5         1813    Disabled
10.1.2.1        Authentication   30       5         1812                       Disabled
```

This example removes a RADIUS server from being used for authentication.
The RADIUS server named 10.1.1.1 is being used for both authentication and accounting.
The Remove-RemoteAccessRadius cmdlet removes the server from being used for authentication.

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
Specifies theIPv4 or IPv6 address, or host name, of the computer on which the Remote Access server computer specific tasks should be run.

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

### -EntrypointName
Specifies the name of the entry point.

Entry point refers to the identity of a site in a multi-site deployment.
It is applicable only to RADIUS server configuration for VPN authentication.
It is not applicable to RADIUS accounting and OTP.

If this parameter is specified, then the RADIUS server for VPN authentication for only that site are retrieved.
To retrieve all RADIUS servers for VPN authorization, a script should be created.

If an entry point is not specified in a multi-site deployment, then the entry point to which the server on which this cmdlet is run is used.
The server could also be represented by using the **ComputerName** parameter.

If this parameter and the **ComputerName** parameter are specified and the **ComputerName** does not belong to the site represented by this parameter, then this parameter takes precedence and the RADIUS server is added to it.

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

### -Purpose
Specifies the purpose of the external RADIUS server.
The acceptable values for this parameter are:

 -- Authentication.

 -- Accounting.

 -- Otp.

If this parameter is omitted, then the RADIUS servers that matches any of the above purposes will be presented.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Authentication, Accounting, Otp

Required: False
Position: 1
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance[]

### Microsoft.Management.Infrastructure.CimInstance#RemoteAccessRadiusServer

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The array of RemoteAccessRadiusServer objects consists of the following properties:

An array of such objects is output with one object for each RADIUS server.
If a RADIUS server is used for more than one purpose, then a separate instance is output for each instance.

 -- IPv4 or IPv6 address or host name of the RADIUS server.

 -- The purpose of the server: VPN authentication, accounting or OTP.

 -- RADIUS initial score.

 -- RADIUS timeout in seconds.

 -- RADIUS port number.

 -- RADIUS shared secret.
For security reasons, this property is never populated and will always show as blank.

 -- Status of accounting on/off messages: if the RADIUS server is used for authentication or OTP, then this property is always blank.

 -- Status of message authenticator: if the RADIUS server is used for accounting or OTP, then this property is always blank.

## NOTES

## RELATED LINKS

[Remove-RemoteAccessRadius](./Remove-RemoteAccessRadius.md)

