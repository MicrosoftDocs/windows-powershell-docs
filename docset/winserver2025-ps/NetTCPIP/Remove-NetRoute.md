---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetRoute.cdxml-help.xml
Module Name: NetTCPIP
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nettcpip/remove-netroute?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-NetRoute
---

# Remove-NetRoute

## SYNOPSIS
Removes IP routes from the IP routing table.

## SYNTAX

### ByName (Default)
```
Remove-NetRoute [[-DestinationPrefix] <String[]>] [-InterfaceIndex <UInt32[]>] [-InterfaceAlias <String[]>]
 [-NextHop <String[]>] [-AddressFamily <AddressFamily[]>] [-Publish <Publish[]>] [-RouteMetric <UInt16[]>]
 [-Protocol <Protocol[]>] [-CompartmentId <UInt32[]>] [-ValidLifetime <TimeSpan[]>]
 [-PreferredLifetime <TimeSpan[]>] [-State <State[]>] [-InterfaceMetric <UInt32[]>]
 [-AssociatedIPInterface <CimInstance>] [-PolicyStore <String>] [-IncludeAllCompartments]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Remove-NetRoute -InputObject <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-NetRoute** cmdlet removes IP routes from the IP routing table.
Run this cmdlet without any parameters to remove all IP routes from the routing table, including default routes.
You can also specify routes to remove by specifying parameters, or by using the Get-NetRoute cmdlet.

For more information about routing, see Chapter 5 - [IP Routing](https://technet.microsoft.com/library/bb727001.aspx) in the TechNet library.

## EXAMPLES

### Example 1: Remove all routes
```
PS C:\>Remove-NetRoute
```

This command removes all of the IP routes on the computer, including default routes.

### Example 2: Remove routes for a specified next hop
```
PS C:\>Remove-NetRoute -NextHop "192.168.0.1"
```

This command removes all of the IP routes that have a next hop of 192.168.0.1.

## PARAMETERS

### -AddressFamily
Specifies an array of IP address families of IP routes.
The cmdlet removes IP routes that belong to the families that you specify.
The acceptable values for this parameter are:

- IPv4
- IPv6

```yaml
Type: AddressFamily[]
Parameter Sets: ByName
Aliases:
Accepted values: IPv4, IPv6

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -AssociatedIPInterface
Specifies an IP interface as a **CIM** object.
The cmdlet removes IP routes that belong to the interfaces that you specify.
To obtain an IP interface, use the Get-NetIPInterface cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -CompartmentId
Specifies an array of identifiers for network compartments in the protocol stack.
By default, the cmdlet only removes Net routes in the default compartment.
If you specify a value, the cmdlet removes any matching Net routes in all compartments in this field.

```yaml
Type: UInt32[]
Parameter Sets: ByName
Aliases:

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

### -DestinationPrefix
Specifies an array of destination prefixes of IP routes.
The cmdlet removes IP routes that use the prefixes that you specify.
A destination prefix contains an IP address prefix and a prefix length, separated by a slash (/).
A value of 0.0.0.0/0 for IPv4 or ::/0 for IPv6 indicates that the value of the **NextHop** parameter is a default gateway.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeAllCompartments
Indicates that the cmdlet includes routes from all configured network compartments.
If you do not specify this parameter, the cmdlet removes only routes in the default network compartment.

```yaml
Type: SwitchParameter
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InterfaceAlias
Specifies an array of aliases of network interfaces.
The cmdlet removes IP routes for the interfaces that have the aliases that you specify.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: ifAlias

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceIndex
Specifies an array of indexes of network interfaces.
The cmdlet removes IP routes for the interfaces located at the indexes that you specify.

```yaml
Type: UInt32[]
Parameter Sets: ByName
Aliases: ifIndex

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceMetric
Specifies an array of integer interface metrics for network interfaces. The cmdlet gets IP routes
for the interfaces that have the metric that you specify.

```yaml
Type: UInt32[]
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NextHop
Specifies an array of next hop values.
The cmdlet removes routes that have the next hop values that you specify.
A value of 0.0.0.0 for IPv4 or :: for IPv6 indicates that the route is on the local subnet.

```yaml
Type: String[]
Parameter Sets: ByName
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

### -PolicyStore
Specifies a **PolicyStore** value.
The cmdlet removes IP routes that have the **PolicyStore** value that you specify.
The acceptable values for this parameter are:

- ActiveStore.
The IP address information is valid.
- PersistentStore.
The computer saves IP address information across restarts.
When the computer restarts, it copies the saved settings to the ActiveStore.

```yaml
Type: String
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreferredLifetime
Specifies an array of values for preferred lifetime, as **TimeSpan** objects, of IP routes.
The cmdlet removes IP routes that have the lifetimes that you specify.
To obtain a **TimeSpan** object, use the New-TimeSpan cmdlet.
For more information, type `Get-Help New-TimeSpan`.

```yaml
Type: TimeSpan[]
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol
Specifies an array of types of routing protocols.
The cmdlet removes IP routes that use the protocols that you specify.
The acceptable values for this parameter are:

- Bbn
- Bgp
- Dhcp
- Dvmrp
- Egp
- Eigrp
- EsIs
- Ggp
- Hello
- Icmp
- Idpr
- Igrp
- IsIs
- Local
- NetMgmt
- Ospf
- Rip
- Rpl
- Other

```yaml
Type: Protocol[]
Parameter Sets: ByName
Aliases:
Accepted values: Other, Local, NetMgmt, Icmp, Egp, Ggp, Hello, Rip, IsIs, EsIs, Igrp, Bbn, Ospf, Bgp, Idpr, Eigrp, Dvmrp, Rpl, Dhcp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Publish
Specifies an array of publish settings of IP routes.
The cmdlet removes IP routes that have the publish settings that you specify.
The acceptable values for this parameter are:

- No.
Do not publish or advertise IP route information in router advertisements.
- Yes.
Publish and advertise IP route information that includes an infinite valid lifetime in router advertisements
- Age.
Publish and advertise IP route information with a finite valid lifetime in router advertisements.

```yaml
Type: Publish[]
Parameter Sets: ByName
Aliases:
Accepted values: No, Age, Yes

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RouteMetric
Specifies an array of integer route metrics for IP routes.
The cmdlet removes IP routes that have the metrics that you specify.
To choose among multiple routes, the computer adds this value to the interface metric value.
The computer selects the route with the lowest combined value.
To modify the interface metric, use the Set-NetIPInterface cmdlet.

```yaml
Type: UInt16[]
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -State
Specifies an array of state values for IP routes. The cmdlet gets entries that have the state values
that you specify.

```yaml
Type: State[]
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell&reg; calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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

### -ValidLifetime
Specifies an array of values for valid lifetime, as a **TimeSpan** object, for IP routes.
The cmdlet removes IP routes that have the lifetime that you specify.
To obtain a **TimeSpan** object, use the New-TimeSpan cmdlet.

```yaml
Type: TimeSpan[]
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### Microsoft.Management.Infrastructure.CimInstance#rootStandardCimv2MSFT_NetRoute
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Find-NetRoute](./Find-NetRoute.md)

[Get-NetRoute](./Get-NetRoute.md)

[New-NetRoute](./New-NetRoute.md)

[Set-NetRoute](./Set-NetRoute.md)

[Get-NetIPInterface](./Get-NetIPInterface.md)

