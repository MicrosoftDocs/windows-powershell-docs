---
external help file: NetTCPIP_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 3FFBE8B0-365B-45AD-9237-6FA5FA01438A
manager: dansimp
---

# Get-NetRoute

## SYNOPSIS
Gets the IP routing table.

## SYNTAX

```
Get-NetRoute [[-DestinationPrefix] <String[]>] [-AddressFamily <AddressFamily[]>] [-AsJob]
 [-AssociatedIPInterface <CimInstance>] [-CimSession <CimSession[]>] [-InterfaceAlias <String[]>]
 [-InterfaceIndex <UInt32[]>] [-NextHop <String[]>] [-PolicyStore <String>] [-PreferredLifetime <TimeSpan[]>]
 [-Publish <Publish[]>] [-RouteMetric <UInt16[]>] [-ThrottleLimit <Int32>] [-ValidLifetime <TimeSpan[]>]
```

## DESCRIPTION
The **Get-NetRoute** cmdlet gets the IP routing table information, including destination network prefixes, Next Hop IP addresses and Route Metrics.

IP routing is the process of forwarding a packet based on the destination IP address.
Routing occurs at a sending TCP/IP host and at an IP router. 

In each case, the IP layer at the sending host or router must decide where to forward the packet.
For IPv4, routers are also commonly referred to as gateways.
To make these decisions, the IP layer consults a routing table stored in memory.
Routing table entries are created by default when TCP/IP initializes, and entries can be added either manually or automatically.
When the computer is routing, the RouteMetric property is added to the InterfaceMetric property, described as a part of NetIPInterface.
This total value is used to decide the pass-through interface to send the forwarded packets.
For more information, see IP Routing on TechNethttp://technet.microsoft.com/library/bb727001.aspx.

Note: A gateway is a routing concept covered by this cmdlet.
For IP endpoints, the gateway specifies the forwarding or next hop IP address over which the set of addresses defined by the network destination and subnet mask are reachable.

Without parameters, this cmdlet returns the routing table for all routes on the computer.

## EXAMPLES

### EXAMPLE 1
```
Used without parameters, this cmdlet gets IP route information for all interfaces.
PS C:\>Get-NetRoute


The default output omits some properties. Run this cmdlet to display all of the fields (all of the properties of the object).
PS C:\>Get-NetRoute | Format-List -Property *
```

This example gets information about IP route configuration.

### EXAMPLE 2
```
PS C:\>Get-NetRoute -AddressFamily IPv6
```

This example gets information about the IP route configuration for IPv6 routes.

### EXAMPLE 3
```
PS C:\>Get-NetRoute | Format-List
```

This example gets information about IP route configuration, and displays more information than the default table view.
This includes properties such as InterfaceAlias, ValidLifetime, and PreferredLifetime.

### EXAMPLE 4
```
PS C:\>Get-NetRoute -InterfaceIndex 12
```

This example gets information about IP route configuration for all routes that use a specific InterfaceIndex.

### EXAMPLE 4
```
PS C:\>Get-NetRoute -DestinationPrefix "0.0.0.0/0" | Select-Object -Expand NextHop
```

This example gets the default IP routes, finds one or more NextHop IP addresses, and displays them.
Note: The next hop gateway for the default route is also known as the default gateway.

### EXAMPLE 5
```
PS C:\>Get-NetRoute | Where-Object -FilterScript { $_.NextHop -Ne "::" } | Where-Object -FilterScript { $_.NextHop -Ne "0.0.0.0" } | Where-Object -FilterScript { ($_.NextHop.SubString(0,6) -Ne "fe80::") }
```

This example gets information about IP routes that access destinations off-link.

### EXAMPLE 6
```
PS C:\>Get-NetRoute | Where-Object -FilterScript {$_.NextHop -Ne "::"} | Where-Object -FilterScript { $_.NextHop -Ne "0.0.0.0" } | Where-Object -FilterScript { ($_.NextHop.SubString(0,6) -Ne "fe80::") } | Get-NetAdapter
```

This example gets information about network adapters that have IP routes that access destinations off-link.

### EXAMPLE 7
```
PS C:\>Get-NetRoute | Where-Object -FilterScript { $_.ValidLifetime -Eq ([TimeSpan]::MaxValue) }


Similarly, this command gets information about IP Routes that do not have an infinite ValidLifetime.
PS C:\>Get-NetRoute | Where-Object -FilterScript { $_.ValidLifetime -Ne ([TimeSpan]::MaxValue) }
```

This example gets information about IP Routes that have an infinite ValidLifetime.

## PARAMETERS

### -AddressFamily
Gets IP routes by IP address family.
The acceptable values for this parameter are:

 -- IPv4: IPv4 route information. 

 -- IPv6: IPv6 route information.

```yaml
Type: AddressFamily[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -AssociatedIPInterface
Gets IP routes by a specific network IP interface CIM object.
This is typically as input through the pipeline.

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

### -DestinationPrefix
Gets IP routes by destination prefix.
This parameter value contains an IP address prefix and a prefix length, separated by a slash (/).
A DestinationPrefix of `0.0.0.0/0` for IPv4 or `::/0` for IPv6 would indicate that the NextHop is a default gateway.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: Dhcp
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterfaceAlias
Gets IP routes by a specific interface, as defined by the interface alias.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceIndex
Gets IP routes by a specific interface, as defined by the InterfaceIndex number.Specifies the user-friendly interface index number.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NextHop
Gets IP routes by next hop.
This parameter value is the IP address of the next hop in the route.
A NextHop of `0.0.0.0` for IPv4 or `::` for IPv6 would indicate that the route is on-link.

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
Specifies the PolicyStore value.
The acceptable values for this parameter are:

 -- ActiveStore: The IP address information is currently valid. 

 -- PersistentStore: The IP address information is persistent across reboots.
When the computer starts, the PersistentStore settings are copied to the ActiveStore. 

The default value is ActiveStore.

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
Gets IP routes by preferred lifetime.
This parameter value uses time as defined by the TimeSpanhttp://msdn.microsoft.com/library/system.timespan.aspx structure.

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

### -Publish
Gets the IP routes by publish property.
By default, routes are not published and thus not advertised in Router Advertisements (No).
This is the default.
Routes may be published (Yes) and advertised in router advertisements with an infinite ValidLifetime.
Routes may also be published (Age) and advertised in Router Advertisements with a finite ValidLifetime.
The acceptable values for this parameter are:

 -- No: The IP Route information is currently from unpublished routes. 

 -- Yes: The IP Route information is currently from published routes with an infinite lifetime. 

 -- Age: The IP Route information is currently from published routes with a finite lifetime.

```yaml
Type: Publish[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RouteMetric
Gets IP routes by route metric.
This parameter value specifies an integer cost metric for the route.
This parameter value is added to the **InterfaceMetric** parameter value and the total value is used when choosing among multiple routes in the routing table that most closely match the destination address of a packet being forwarded.
The route with the lowest, combined RouteMetric property and InterfaceMetric property value is chosen.

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

### -ValidLifetime
Gets IP routes by valid lifetime.
This parameter value uses time as defined by the TimeSpanhttp://msdn.microsoft.com/library/system.timespan.aspx structure.

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

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetRoute
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Format-List](https://go.microsoft.com/fwlink/?LinkId=113302)

[Select-Object](https://go.microsoft.com/fwlink/?LinkId=113387)

[Where-Object](https://go.microsoft.com/fwlink/?LinkId=113423)

[New-NetRoute](./New-NetRoute.md)

[Remove-NetRoute](./Remove-NetRoute.md)

[Set-NetRoute](./Set-NetRoute.md)

[Get-NetAdapter](../netadapter/Get-NetAdapter.md)

