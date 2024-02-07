---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DAAppServerConnection_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/set-daappserverconnection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DAAppServerConnection
---

# Set-DAAppServerConnection

## SYNOPSIS
Configures the properties of the connection to application servers and the IPsec security traffic protection policies for the connection.

## SYNTAX

```
Set-DAAppServerConnection [-ConnectionType <String>] [-TrafficProtection <String>] [-ComputerName <String>]
 [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-DAAppServerConnection** cmdlet configures the properties of the connection to application servers and the IPsec security traffic protection policies for the connection.
This cmdlet is not applicable when DirectAccess (DA) is deployed only for the management of remote clients and when no application servers have been configured.

## EXAMPLES

### EXAMPLE 1
```
This cmdlet checks the connection type setting that is configured.
PS C:\>Get-DAAppServer -ComputerName edge1.corp.contoso.com
SecurityGroupNameList:    {corp.contoso.com\daappservergrp}
GpoName              :    {corp.contoso.com\DirectAccess Application Server Settings}
ConnectionType       :    E2EAuthOnlyToAppServer
TrafficProtection    :    Enabled

This cmdlet changes the value of the **ConnectionType** parameter from authentication required only to application servers (E2EAuthOnlyToAppServer) to mandatory authentication for all servers in the corporate network (E2EAuthRequiredToAllServer).
PS C:\>Set-DAAppServerConnection -ConnectionType E2EAuthRequiredToAllServers -TrafficProtection Enabled -PassThru
ConnectionType       :    E2EAuthRequiredToAllServer
TrafficProtection    :    Enabled
```

This example enables end to end authentication for all servers in organization.

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
Specifies the IPv4 or IPv6 address, or host name of the computer, on which the Remote Access server computer specific tasks should be run.

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

### -ConnectionType
Specifies the type of connection to the corporate network.
The acceptable values for this parameter are:


- NoE2EAuth.
Connection requires no end-to-end authentication.

- E2EAuthOnlyToAppServer.
Connection requires end-to-end authentication only to the configured application servers and not to other servers in the corporate network.

- E2EAuthRequiredToAllServers.
Connection permits access only to the configured application servers through end-to-end authentication and does not permit access to other servers in the corporate network.


If you specify NoE2EAuth, the cmdlet automatically removes all the application server security groups and Group Policy Objects from the DA deployment, and the user can access all the corporate network servers over a full tunnel to the DA server.
IPsec security traffic protection is not applicable for the connection if you specify NoE2EAuth as the connection type.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: NoE2EAuth, E2EAuthOnlyToAppServer, E2EAuthRequiredToAllServers

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns the application server connection object which contains the properties of the connectivity to the corporate network.
By default this cmdlet does not generate any output.

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

### -TrafficProtection
Specifies the property of the IPsec connection to the application servers.
IPsec traffic protection is not applicable for the connection if you specify NoE2EAuth for the **ConnectionType** parameter.
The acceptable values for this parameter are:


- Enabled.
Traffic protection is enabled.

- Disabled.
Traffic protection is disabled and the connection requires authentication.

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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#DAAppServerConnection

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The DAAppServerConnection object consists of the following properties:

 -- The property of the connection to an application server.

 -- The status of IPsec traffic protection: Enabled or Disabled.

 -- The application server connectivity properties are applicable to all application servers in the DA deployment.

## NOTES

## RELATED LINKS

[Add-DAAppServer](./Add-DAAppServer.md)

[Get-DAAppServer](./Get-DAAppServer.md)

[Remove-DAAppServer](./Remove-DAAppServer.md)

