---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetRoute.cdxml-help.xml
Module Name: NetTCPIP
ms.date: 06/23/2021
online version: https://learn.microsoft.com/powershell/module/nettcpip/get-netroute?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetRoute
---

# Get-NetRoute

## SYNOPSIS
Gets the IP route information from the IP routing table.

## SYNTAX

```
Get-NetRoute [[-DestinationPrefix] <String[]>] [-InterfaceIndex <UInt32[]>] [-InterfaceAlias <String[]>]
 [-NextHop <String[]>] [-AddressFamily <AddressFamily[]>] [-Publish <Publish[]>] [-RouteMetric <UInt16[]>]
 [-Protocol <Protocol[]>] [-CompartmentId <UInt32[]>] [-ValidLifetime <TimeSpan[]>]
 [-PreferredLifetime <TimeSpan[]>] [-State <State[]>] [-InterfaceMetric <UInt32[]>]
 [-AssociatedIPInterface <CimInstance>] [-PolicyStore <String>] [-IncludeAllCompartments]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetRoute** cmdlet gets IP route information from the IP routing table, including destination network prefixes, next hop IP addresses, and route metrics.
Run this cmdlet without any parameters to get all IP routes from the routing table.
Specify parameters to narrow your results.
For instance, you can specify a particular interface or an IP address family.

For more information about routing, see Chapter 5 - [IP Routing](https://technet.microsoft.com/library/bb727001.aspx) in the TechNet library.

## EXAMPLES

### Example 1: Get all routes
```
PS C:\>Get-NetRoute | Format-List -Property *
```

This command gets all the routes for the computer, and then passes them to the Format-List cmdlet by using the pipeline operator.
The **Format-List** cmdlet displays all the properties of an object.
For more information, type `Get-Help Format-List`.

### Example 2: Get all IPv6 routes
```
PS C:\>Get-NetRoute -AddressFamily IPv6
```

This command gets the routes that belong to the IPv6 address family.

### Example 3: Get routes for a specified interface
```
PS C:\>Get-NetRoute -InterfaceIndex 12
```

This command gets the IP routes associated with the interface that has an index of 12.

### Example 4: Get the next hop for the default route
```
PS C:\>Get-NetRoute -DestinationPrefix "0.0.0.0/0" | Select-Object -ExpandProperty "NextHop"
```

This command gets the next hop for the default route.
The next hop gateway for the default route is also known as the default gateway.
The command gets the default IP routes, and passes them to the Select-Object cmdlet.
That cmdlet displays the **NextHop** property for each default route.
For more information about displaying selected properties, type `Get-Help Select-Object`.

### Example 5: Get IP routes to non-local destinations
```
PS C:\>Get-NetRoute | Where-Object -FilterScript { $_.NextHop -Ne "::" } | Where-Object -FilterScript { $_.NextHop -Ne "0.0.0.0" } | Where-Object -FilterScript { ($_.NextHop.SubString(0,6) -Ne "fe80::") }
```

This command gets IP routes that have next hops that are not in the local subnet.
The command gets all routes, and then passes them to a series of Where-Object commands by using the pipeline operator.
The command uses different filter scripts to discard routes that are the default gateway for the two IP address families and the IPv6 addresses that begin with fe80.
For more information about filtering by using **Where-Object**, type `Get-Help Where-Object`.

### Example 6: Get network adapters that have IP routes to non-local destinations
```
PS C:\>Get-NetRoute | Where-Object -FilterScript {$_.NextHop -Ne "::"} | Where-Object -FilterScript { $_.NextHop -Ne "0.0.0.0" } | Where-Object -FilterScript { ($_.NextHop.SubString(0,6) -Ne "fe80::") } | Get-NetAdapter
```

This command gets network adapters that have IP routes that have next hops that are not in the local subnet.
As in the previous example, the command gets the routes that have next hop values by using the **Get-NetRoute** and the Where-Object cmdlets, and then passes those routes to the **Get-NetAdapter** cmdlet by using the pipeline operator.

### Example 7: Get IP routes that have an infinite valid lifetime
```
PS C:\>Get-NetRoute | Where-Object -FilterScript { $_.ValidLifetime -Eq ([TimeSpan]::MaxValue) }
```

This command gets all IP routes, and then passes them to the Where-Object cmdlet by using the pipeline operator.
The command selects those routes that have a valid lifetime of the maximum value.

## PARAMETERS

### -AddressFamily
Specifies an IP address family.
The cmdlet gets IP routes of the families that you specify.
The acceptable values for this parameter are:

- IPv4
- IPv6

```yaml
Type: AddressFamily[]
Parameter Sets: (All)
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
The cmdlet gets IP routes that belong to the interface that you specify.
To obtain an IP interface, use the Get-NetIPInterface cmdlet.

```yaml
Type: CimInstance
Parameter Sets: (All)
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
By default, the cmdlet only gets Net routes in the default compartment.
If you specify a value, the cmdlet gets any matching Net routes in all compartments in this field.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationPrefix
Specifies an array of destination prefixes of IP routes.
The cmdlet gets IP routes that use the prefixes that you specify.
A destination prefix contains an IP address prefix and a prefix length, separated by a slash (/).
A value of 0.0.0.0/0 for IPv4 or ::/0 for IPv6 indicates that the value of the *NextHop* parameter is a default gateway.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeAllCompartments
Indicates that the cmdlet includes routes from all configured network compartments.
If you do not specify this parameter, the cmdlet gets only routes in the default network compartment.

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

### -InterfaceAlias
Specifies an array of aliases of network interfaces.
The cmdlet gets IP routes for the interfaces that have the aliases that you specify.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: ifAlias

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceIndex
Specifies an array of indexes of network interfaces.
The cmdlet gets IP routes for the interfaces located at the indexes that you specify.

```yaml
Type: UInt32[]
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NextHop
Specifies an array of next hop values.
The cmdlet gets IP routes that have the next hop values that you specify.
A value of 0.0.0.0 for IPv4 or :: for IPv6 indicates that the route is on the local subnet.

```yaml
Type: String[]
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
The cmdlet gets IP routes that have the **PolicyStore** value that you specify.
The acceptable values for this parameter are:

- ActiveStore.
The IP address information is valid.
- PersistentStore.
The computer saves IP address information across restarts.
When the computer restarts, it copies the saved settings to the ActiveStore.

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

### -PreferredLifetime
Specifies an array of values for preferred lifetime, as **TimeSpan** objects, of IP routes.
The cmdlet gets entries that have these values.
To obtain a **TimeSpan** object, use the New-TimeSpan cmdlet.
For more information, type `Get-Help New-TimeSpan`.

```yaml
Type: TimeSpan[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol
Specifies an array of types of routing protocols.
The cmdlet gets entries that use the protocols that you specify.
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
Parameter Sets: (All)
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
The cmdlet gets entries that have the publish values that you specify.
The acceptable values for this parameter are:

- No.
Do not publish or advertise IP route information in router advertisements.
- Yes.
Publish and advertise IP route information with an infinite valid lifetime in router advertisements
- Age.
Publish and advertise IP route information with a finite valid lifetime in router advertisements.

```yaml
Type: Publish[]
Parameter Sets: (All)
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
The cmdlet gets entries that have the metrics that you specify.
To choose among multiple routes, the computer adds this value to the interface metric value.
The computer selects the route with the lowest combined value.
To modify the interface metric, use the Set-NetIPInterface cmdlet.

```yaml
Type: UInt16[]
Parameter Sets: (All)
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
Specifies an array of values for valid lifetimes, as **TimeSpan** objects, for IP routes.
The cmdlet gets entries that have the lifetimes that you specify.
To obtain a **TimeSpan** object, use the **New-Timespan** cmdlet.

```yaml
Type: TimeSpan[]
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetRoute
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-NetAdapter](../netadapter/Get-NetAdapter.md)

[Find-NetRoute](./Find-NetRoute.md)

[Get-NetIPInterface](./Get-NetIPInterface.md)

[New-NetRoute](./New-NetRoute.md)

[Remove-NetRoute](./Remove-NetRoute.md)

[Set-NetRoute](./Set-NetRoute.md)

