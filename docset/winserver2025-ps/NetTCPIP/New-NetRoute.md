---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetRoute.cdxml-help.xml
Module Name: NetTCPIP
ms.date: 05/30/2018
online version: https://learn.microsoft.com/powershell/module/nettcpip/new-netroute?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetRoute
---

# New-NetRoute

## SYNOPSIS
Creates a route in the IP routing table.

## SYNTAX

### ByInterfaceAlias (Default)
```
New-NetRoute [-DestinationPrefix] <String> -InterfaceAlias <String> [-AddressFamily <AddressFamily>]
 [-NextHop <String>] [-PolicyStore <String>] [-Publish <Publish>] [-RouteMetric <UInt16>]
 [-Protocol <Protocol>] [-ValidLifetime <TimeSpan>] [-PreferredLifetime <TimeSpan>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInterfaceIndex
```
New-NetRoute [-DestinationPrefix] <String> [-AddressFamily <AddressFamily>] [-NextHop <String>]
 [-PolicyStore <String>] [-Publish <Publish>] [-RouteMetric <UInt16>] [-Protocol <Protocol>]
 [-ValidLifetime <TimeSpan>] [-PreferredLifetime <TimeSpan>] -InterfaceIndex <UInt32>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-NetRoute** cmdlet creates an IP route in the IP routing table.
Specify the destination prefix, and specify an interface by using the interface alias or the interface index.

IP routing is the process of forwarding a packet based on the destination IP address.
Routing occurs at TCP/IP hosts and at IP routers.
The sending host or router determines where to forward the packet.
To determine where to forward a packet, the host or router consults a routing table that is stored in memory.
When TCP/IP starts, it creates entries in the routing table.
You can add entries either manually or automatically.

For more information about routing, see Chapter 5 - [IP Routing](https://technet.microsoft.com/library/bb727001.aspx) in the TechNet library.

## EXAMPLES

### Example 1: Add an IP route to the routing table
```
PS C:\>New-NetRoute -DestinationPrefix "10.0.0.0/24" -InterfaceIndex 12 -NextHop 192.168.0.1
PS C:\>Get-NetRoute | Format-List -Property *
```

This example adds a routing table entry, and then displays the properties of all the entries in the routing table.

The first command creates a route for the destination prefix 10.0.0.0/24 for the interface that has the index of 12.
The command specifies 192.168.0.1 as the next hop.

The second command uses the Get-NetRoute cmdlet to get all the routes for the computer, and then passes them to the Format-List cmdlet by using the pipeline operator.
The **Format-List** cmdlet can display all the properties of an object.
For more information, type `Get-Help Format-List`.

## PARAMETERS

### -AddressFamily
Specifies the IP address family.
The cmdlet uses the family that you specify for the IP route.
The acceptable values for this parameter are:

- IPv4
- IPv6

If you do not specify this parameter, the cmdlet selects a value based on the other input that you provide.

```yaml
Type: AddressFamily
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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/New-CimSession) or [Get-CimSession](/powershell/module/cimcmdlets/Get-CimSession) cmdlet.
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
Specifies a destination prefix of an IP route.
A destination prefix consists of an IP address prefix and a prefix length, separated by a slash (/).
A value of 0.0.0.0/0 for IPv4 or ::/0 for IPv6 indicates that the value of the *NextHop* parameter is a default gateway.
The prefix length of the local host must match the prefix specified in this parameter, with all remaining address fields set to zero.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterfaceAlias
Specifies the alias of a network interface.
The cmdlet adds a route for the interface that has the alias that you specify.

```yaml
Type: String
Parameter Sets: ByInterfaceAlias
Aliases: ifAlias

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceIndex
Specifies the index of a network interface.
The cmdlet adds a route for the interface located at the index that you specify.

```yaml
Type: UInt32
Parameter Sets: ByInterfaceIndex
Aliases: ifIndex

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NextHop
Specifies the next hop for the IP route.
The cmdlet assigns the next hop that you specify to the IP route.
A value of 0.0.0.0 for IPv4 or :: for IPv6 indicates that the route is on the local subnet.

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
Specifies the **PolicyStore** value.
The cmdlet assigns the **PolicyStore** value that you specify to the IP route.
The acceptable values for this parameter are:

- ActiveStore. Current routing information, used by the OS.
When a computer reboots, information in this store is lost.
- PersistentStore. Cannot be used. Routing information in this store preserved across reboots.
When a computer starts, it copies the saved settings from this store to the ActiveStore.

By default, a route is saved in both stores. Use this parameter only when you need to create a route in just the ActiveStore.

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
Specifies a preferred lifetime, as a **TimeSpan** object, of an IP route.
The cmdlet assigns the lifetime that you specify to the IP route.
To obtain a **TimeSpan** object, use the New-TimeSpan cmdlet.
For more information, type `Get-Help New-TimeSpan`.
The default value for a lifetime is infinite.

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

### -Protocol
Specifies the type of routing protocol.
The cmdlet assigns the protocol that you specify to the IP route.
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

The default value is NetMgmt.

```yaml
Type: Protocol
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
Specifies the publish setting of an IP route.
The cmdlet assigns the publish setting that you specify to the IP route.
The acceptable values for this parameter are:

- No.
Do not publish or advertise IP route information in router advertisements.
- Yes.
Publish and advertise IP route information with an infinite valid lifetime in router advertisements.
- Age.
Publish and advertise IP route information with a finite valid lifetime in router advertisements.
Specify a valid lifetime by using the *ValidLifetime* parameter.

The default value is No.

```yaml
Type: Publish
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
Specifies an integer route metric for an IP route.
The cmdlet assigns the metric that you specify to the IP route.
The default value is 256.
To choose among multiple routes, the computer adds this value.
The computer selects the route with the lowest combined value.
To modify the interface metric, use the Set-NetIPInterface cmdlet.

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
Specifies a valid lifetime, as a **TimeSpan** object, for an IP route.
The cmdlet assigns the lifetime setting that you specify to the IP route.
To obtain a **TimeSpan** object, use the New-TimeSpan cmdlet.
The default value is infinite.

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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetRoute
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Find-NetRoute](./Find-NetRoute.md)

[Get-NetRoute](./Get-NetRoute.md)

[Remove-NetRoute](./Remove-NetRoute.md)

[Set-NetRoute](./Set-NetRoute.md)

[Set-NetIPInterface](./Set-NetIPInterface.md)
