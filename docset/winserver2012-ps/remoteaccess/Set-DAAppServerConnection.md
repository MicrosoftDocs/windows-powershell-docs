---
external help file: UnifiedRA_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: AE8D051D-1BF2-4E04-A963-2572AD303DF5
manager: dansimp
---

# Set-DAAppServerConnection

## SYNOPSIS
Configures the properties of the connection to application servers and the IPsec security traffic protection policies for the connection.

## SYNTAX

```
Set-DAAppServerConnection [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-ConnectionType <String>] [-PassThru] [-ThrottleLimit <Int32>] [-TrafficProtection <String>] [-Confirm]
 [-WhatIf]
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
Aliases: 

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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionType
This parameter specifies the type of connection to the corporate network.
The acceptable values for this parameter are:

 -- NoE2EAuth: No end-to-end authentication required. 

 -- E2EAuthOnlyToAppServer: End-to-end authentication required only to the configured application servers and not to other servers in the corporate network. 

 -- E2EAuthRequiredToAllServers: Access allowed only to the configured application servers via end-to-end authentication and no access to other servers in the corporate network. 

If NoE2EAuth is specified, the cmdlet automatically remove all the app server security groups and Group Policy objects from the DA deployment and the user has access to all the corporate network servers over a full tunnel to the DA server. 

IPsec traffic protection is not applicable when the connection type is NoE2EAuth and therefore cannot be configured.

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
This parameter determines the property of the IPsec connection to the application servers.
The acceptable values for this parameter are:

 -- Enabled: This means traffic protection is enabled. 

 -- Disabled: This means that traffic protection is disabled and only authentication will be performed. 

IPsec traffic protection is not applicable when the **ConnectionType** parameter is specified as NoE2EAuth and therefore cannot be configured.

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
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

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

