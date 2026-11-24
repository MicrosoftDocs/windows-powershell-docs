---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DAAppServer_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-daappserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DAAppServer
---

# Get-DAAppServer

## SYNOPSIS
Displays the list of application server security groups that are part of the DirectAccess (DA) deployment and the properties of the connections made to the application servers in the groups.

## SYNTAX

```
Get-DAAppServer [-ComputerName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-DAAppServer** cmdlet displays the list of application server security groups that are part of the DirectAccess (DA) deployment and the properties of the connections made to the application servers in the groups.
This cmdlet is not applicable when DA is deployed only for the management of remote clients.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-DAAppServer -ComputerName edge1.corp.contoso.com
SecurityGroupNameList : {corp.contoso.com\daappservergrp}
GpoName               : {corp.contoso.com\DirectAccess Application Server Settings}
ConnectionType        : E2EAuthOnlyToAppServer
TrafficProtection     : Enabled
```

This example lists the application security groups and the application servers Group Policy Objects (GPOs) configured with DA.
Since application server settings are global to DA configuration, the ConnectionType and, TrafficProtection are the same for all application servers.
These settings can change using the Set-DAAppServerConnection cmdlet.

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
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the Remote Access server computer specific tasks should be run.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#DAAppServer

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The object consists of the following properties:

The list of application server security groups.
Each security group is specified in the `Domain\GroupName` format.

The list of application server GPOs.
Each GPO is specified in the `Domain\GPOName` format.

The properties of the connection to the application server.
If there are no application servers configured, then the default value is NoE2EAuth, which means no end-to-end authentication is required.

Whether or not IPsec traffic protection is enabled.
If there are no application servers configured, then the default value is Disabled.

## NOTES

## RELATED LINKS

[Add-DAAppServer](./Add-DAAppServer.md)

[Get-DAAppServer](./Get-DAAppServer.md)

[Remove-DAAppServer](./Remove-DAAppServer.md)

[Set-DAAppServerConnection](./Set-DAAppServerConnection.md)

