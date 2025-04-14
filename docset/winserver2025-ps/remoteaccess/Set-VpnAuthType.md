---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_VPNAuthType_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/set-vpnauthtype?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VpnAuthType
---

# Set-VpnAuthType

## SYNOPSIS
Sets the authentication type to be used for connecting to a VPN.

## SYNTAX

```
Set-VpnAuthType [-Type] <String> [[-RadiusServer] <String>] [[-SharedSecret] <String>]
 [-RadiusTimeout <UInt32>] [-RadiusScore <Byte>] [-RadiusPort <UInt16>] [-ComputerName <String>]
 [-MsgAuthenticator <String>] [-EntrypointName <String>] [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VpnAuthType** cmdlet is only used to toggle from one authentication type to another.
This cmdlet cannot be used to explicitly add any additional RADIUS servers if RADIUS authentication is being used.

 -- The parameters for RADIUS authentication properties, such as the **MsgAuthenticator**, **RadiusPort**, **RadiusScore**, **RadiusServer**, **RadiusTimeout** and **SharedSecret** parameters, are applicable only when the ExternalRadius authentication is configured.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-VpnAuthType -Type "ExternalRadius" -RadiusServer "10.1.1.1" -SharedSecret "s3cr3t" -PassThru
Type             : ExternalRadius
RadiusServerList : {10.1.1.1}
```

This example sets the VPN authentication type to be ExternalRadius.
A RADIUS server is specified along with the shared secret required to communicate with that RADIUS server.

### EXAMPLE 2
```
PS C:\>Set-VpnAuthType -Type "Windows" -PassThru
Type             : Windows
RadiusServerList :
```

This example sets the VPN authentication type to be Windows, which causes authentication to happen on the Remote Access server computer.

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
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the VPN server computer specific tasks should be run.
If this parameter is specified, then the authentication type is configured for that VPN server.

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
Identifies a site in a multi-site deployment for which the authentication type needs to be configured.

If this parameter is not specified in a multi-site deployment, then this parameter value on which the cmdlet is run is used.
The server could also be represented by using the **ComputerName** parameter.

If this parameter and the **ComputerName** parameter are specified and the **ComputerName** does not belong to the site represented by this parameter, then this parameter takes precedence and the authentication type is configured for it.

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

This parameter can be configured only if the **Type** parameter is specified to be ExternalRadius.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

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

### -RadiusPort
Specifies the port number on which the RADIUS server is accepting authentication requests.

The default value is 1813.

This parameter can be configured only if the **Type** parameter is specified to be ExternalRadius.

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

### -RadiusScore
Specifies the initial score.

The default value is 30.

This parameter can be configured only if the **Type** parameter is specified to be ExternalRadius.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases: Score

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RadiusServer
Specifies the IPv4 or IPv6 address, or host name, of the external RADIUS server that is used for accounting.
This parameter can be configured only if the **Type** parameter is specified to be ExternalRadius.

Specifying the corresponding shared secret is mandatory.
The default values can be used for the other parameters.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ServerName

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RadiusTimeout
Specifies the RADIUS time out value, in seconds.

The default value is 5 seconds.

This parameter can be configured only if the **Type** parameter is specified to be ExternalRadius.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: Timeout

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SharedSecret
Specifies the shared secret between the Remote Access server and the specified external RADIUS server which is required for successful communication between the two servers.
Note: The secret is specified in clear text.

This parameter can be configured only if the **Type** parameter is specified to be ExternalRadius.

When specifying a RADIUS server for authentication, it is mandatory to also specify the shared secret.
The default values can be used for the other parameters.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
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

### -Type
Specifies the authentication type.
The acceptable values for this parameter are:

 -- Windows.

 -- ExternalRadius.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Windows, ExternalRadius

Required: True
Position: 1
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

### System.UInt32

### System.Byte

### System.UInt16

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#VpnAuth

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The VpnAuth object consists of the following properties:

 -- Authentication type: Windows or ExternalRadius.

 -- Configured RADIUS servers: If external RADIUS authentication was set, then the configured RADIUS servers are displayed.

## NOTES

## RELATED LINKS

[Get-VpnAuthProtocol](./Get-VpnAuthProtocol.md)

[Set-VpnAuthProtocol](./Set-VpnAuthProtocol.md)

