---
author: Kateyanne
external help file: NetTCPIP_Cmdlets.xml
manager: dansimp
Module Name: NetTCPIP
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/nettcpip/new-netroute?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-NetRoute

## SYNOPSIS
Creates an entry in the IP routing table.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-NetRoute [-DestinationPrefix] <String> [-AddressFamily <AddressFamily>] [-AsJob]
 [-CimSession <CimSession[]>] [-NextHop <String>] [-PolicyStore <String>] [-PreferredLifetime <TimeSpan>]
 [-Publish <Publish>] [-RouteMetric <UInt16>] [-ThrottleLimit <Int32>] [-ValidLifetime <TimeSpan>]
 -InterfaceAlias <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
New-NetRoute [-DestinationPrefix] <String> [-AddressFamily <AddressFamily>] [-AsJob]
 [-CimSession <CimSession[]>] [-NextHop <String>] [-PolicyStore <String>] [-PreferredLifetime <TimeSpan>]
 [-Publish <Publish>] [-RouteMetric <UInt16>] [-ThrottleLimit <Int32>] [-ValidLifetime <TimeSpan>]
 -InterfaceIndex <UInt32> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **New-NetRoute** cmdlet creates an entry in the IP routing table, including properties such as destination network prefixes, Next Hop IP addresses and Route Metrics.

IP routing is the process of forwarding a packet based on the destination IP address.
Routing occurs at a sending TCP/IP host and at an IP router. 

In each case, the IP layer at the sending host or router must decide where to forward the packet.
For IPv4, routers are also commonly referred to as gateways.
To make these decisions, the IP layer consults a routing table stored in memory.
Routing table entries are created by default when TCP/IP initializes, and entries can be added either manually or automatically.
When the computer is routing, the RouteMetric property is added to the InterfaceMetric property, described as a part of NetIPInterface.
This total value is used to decide the pass-through interface to send the forwarded packets.
For more information, see [IP Routing](https://technet.microsoft.com/library/bb727001.aspx) on TechNet.

Note: A gateway is a routing concept covered by the NetRoute cmdlets.
For IP endpoints, the gateway specifies the forwarding or next hop IP address over which the set of addresses defined by the network destination and subnet mask are reachable.

## EXAMPLES

### EXAMPLE 1
```
Used without parameters this cmdlet gets the IP route information for all of the interfaces.
PS C:\>New-NetRoute -InterfaceIndex 12 -DestinationPrefix 10.0.0.0/24 -NextHop 192.168.0.1


The default output omits some properties. Run this cmdlet to display all of the fields (all of the properties of the object).
PS C:\>Get-NetRoute | Format-List -Property *
```

This example adds an IP routing table entry.

## PARAMETERS

### -AddressFamily
Specifies the IP address family for the IP routing table entry.
The acceptable values for this parameter are:

 -- IPv4: IPv4 route information.

 -- IPv6: IPv6 route information.

```yaml
Type: AddressFamily
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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://docs.microsoft.com/en-us/powershell/module/cimcmdlets/New-CimSession) or [Get-CimSession](https://docs.microsoft.com/en-us/powershell/module/cimcmdlets/Get-CimSession) cmdlet.
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
Specifies a DestinationPrefix for the IP routing table entry.
The DestinationPrefix contains an IP address prefix and a prefix length, separated by a slash (/).
A DestinationPrefix of `0.0.0.0/0` for IPv4 or `::/0` for IPv6 would indicate that the NextHop is a default gateway.
The PrefixLength must match the prefix specified in the DestinationPrefix, with all remaining address fields set to zero.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: Dhcp
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterfaceAlias
Specifies the interface to which the IP routing table entry applies, as defined by the interface alias.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceIndex
Specifies the interface to which the IP routing table entry applies, as defined by the InterfaceIndex number.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NextHop
Specifies a next hop for the IP routing table entry.
The NextHop is the IP address of the next hop in the route.
A NextHop of `0.0.0.0` for IPv4 or `::` for IPv6 would indicate that the route is on-link.
When the new routing table entry is created, the next hop IP address is also added as a neighbor cache entry.

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
Specifies a preferred lifetime for the IP routing table entry.
When not specified this parameter is set as infinite.
This parameter uses time as defined by the [TimeSpan](https://msdn.microsoft.com/library/system.timespan.aspx) structure.


```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Publish
Specifies the Publish setting for the IP routing table entry.
The acceptable values for this parameter are:

 -- No: The IP Route information is published and advertised in router advertisements with an infinite ValidLifetime.
This is the default.

 -- Yes: The IP Route information is published and advertised in router advertisements with an infinite ValidLifetime.

 -- Age: The IP Route information is published and advertised in router advertisements with a finite ValidLifetime.

```yaml
Type: Publish
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RouteMetric
Specifies the route metric for the IP routing table entry.
This parameter value specifies an integer cost metric for the route.
This parameter value is added to the **InterfaceMetric** parameter value and the total value is used when choosing among multiple routes in the routing table that most closely match the destination address of a packet being forwarded.
The route with the lowest, combined RouteMetric property and InterfaceMetric property value is chosen.

```yaml
Type: UInt16
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
Specifies a ValidLifetime for the IP routing table entry.
When not specified the ValidLifetime is set as infinite.
ValidLifetime uses time as defined by the [TimeSpan](https://msdn.microsoft.com/library/system.timespan.aspx) structure.

```yaml
Type: TimeSpan
Parameter Sets: (All)
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetRoute
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Format-List](https://go.microsoft.com/fwlink/p/?LinkId=113302)

[Get-NetRoute](./Get-NetRoute.md)

[Remove-NetRoute](./Remove-NetRoute.md)

[Set-NetRoute](./Set-NetRoute.md)

[TimeSpan](https://msdn.microsoft.com/library/system.timespan.aspx)
