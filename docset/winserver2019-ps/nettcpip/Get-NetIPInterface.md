---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetIPInterface.cdxml-help.xml
Module Name: NetTCPIP
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nettcpip/get-netipinterface?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetIPInterface
---

# Get-NetIPInterface

## SYNOPSIS
Gets an IP interface.

## SYNTAX

### ByName (Default)
```
Get-NetIPInterface [-InterfaceIndex <UInt32[]>] [[-InterfaceAlias] <String[]>]
 [-AddressFamily <AddressFamily[]>] [-Forwarding <Forwarding[]>] [-ClampMss <ClampMss[]>]
 [-Advertising <Advertising[]>] [-NlMtuBytes <UInt32[]>] [-InterfaceMetric <UInt32[]>]
 [-NeighborUnreachabilityDetection <NeighborUnreachabilityDetection[]>] [-BaseReachableTimeMs <UInt32[]>]
 [-ReachableTimeMs <UInt32[]>] [-RetransmitTimeMs <UInt32[]>] [-DadTransmits <UInt32[]>]
 [-DadRetransmitTimeMs <UInt32[]>] [-RouterDiscovery <RouterDiscovery[]>]
 [-ManagedAddressConfiguration <ManagedAddressConfiguration[]>]
 [-OtherStatefulConfiguration <OtherStatefulConfiguration[]>] [-WeakHostSend <WeakHostSend[]>]
 [-WeakHostReceive <WeakHostReceive[]>] [-IgnoreDefaultRoutes <IgnoreDefaultRoutes[]>]
 [-AdvertisedRouterLifetime <TimeSpan[]>] [-AdvertiseDefaultRoute <AdvertiseDefaultRoute[]>]
 [-CurrentHopLimit <UInt32[]>] [-ForceArpNdWolPattern <ForceArpNdWolPattern[]>]
 [-DirectedMacWolPattern <DirectedMacWolPattern[]>] [-EcnMarking <EcnMarking[]>] [-Dhcp <Dhcp[]>]
 [-ConnectionState <ConnectionState[]>] [-AutomaticMetric <AutomaticMetric[]>]
 [-NeighborDiscoverySupported <NeighborDiscoverySupported[]>] [-CompartmentId <UInt32[]>]
 [-PolicyStore <String>] [-IncludeAllCompartments] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByRoute
```
Get-NetIPInterface [-AssociatedRoute <CimInstance>] [-IncludeAllCompartments] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByIPAddress
```
Get-NetIPInterface [-AssociatedIPAddress <CimInstance>] [-IncludeAllCompartments] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByNeighbor
```
Get-NetIPInterface [-AssociatedNeighbor <CimInstance>] [-IncludeAllCompartments] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByAdapter
```
Get-NetIPInterface [-AssociatedAdapter <CimInstance>] [-IncludeAllCompartments] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetIPInterface** cmdlet gets an IP interface, including IPv4 and IPv6 addresses, and the associated address configuration for the IP interfaces.
Without parameters, this cmdlet gets all of the IP interface properties on the computer, including virtual interfaces and loopback interfaces.

## EXAMPLES

### Example 1: Get IP interface configuration
```
PS C:\>Get-NetIPInterface
```

This command gets the IP interface configuration on the computer on which you run the cmdlet.

### Example 2: Get IP interface information for IPv6 addresses
```
PS C:\>Get-NetIPInterface -AddressFamily IPv6
```

This command gets information about the IP interface configuration for all IP interfaces for which you have configured IPv6 addresses.

### Example 3: Get IP interface information and format the output
```
PS C:\>Get-NetIPInterface | Format-Table
```

This command gets information about IP interface configuration, and displays that information in a table.

### Example 4: Get IP interface information by interface index
```
PS C:\>Get-NetIPInterface -InterfaceIndex 12
```

This command gets information about the IP interface configuration for a specific interface index.

### Example 5: Get and sort IP interface information
```
PS C:\>Get-NetIPInterface | Sort-Object -Property InterfaceIndex | Format-Table
```

This command gets information about IP address configuration, sorts them numerically by the interface index in the cmdlet name, and then displays them in a table format.

### Example 6: Get the IP interface by specifying the router lifetime
```
PS C:\>Get-NetIPInterface | Where-Object -FilterScript { $_.AdvertisedRouterLifetime.TotalSeconds -Eq 1800 }
```

This command gets information about IP address configuration for all IP interfaces that have a default AdvertisedRouterLifetime.

## PARAMETERS

### -AddressFamily
Specifies an array of IP address families.
The cmdlet gets the IP interface that matches the address families.
The acceptable values for this parameter are:

 -- IPv4
 -- IPv6

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

### -AdvertiseDefaultRoute
Specifies an array of default router advertisement values for an IP interface.
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

```yaml
Type: AdvertiseDefaultRoute[]
Parameter Sets: ByName
Aliases: 
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdvertisedRouterLifetime
Specifies an array of lifetimes, as **TimeSpan** objects, for default routes.
This parameter indicates the lifetime of default routes when advertising routes on the IP interface.
The default value is 1800.
Valid only for advertising interfaces.
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

### -Advertising
Specifies an array of router advertisement values for the IP interface.
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

 The default value is Disabled.

```yaml
Type: Advertising[]
Parameter Sets: ByName
Aliases: 
Accepted values: Disabled, Enabled

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

### -AssociatedAdapter
Specifies a network adapter as a CIM object.

```yaml
Type: CimInstance
Parameter Sets: ByAdapter
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AssociatedIPAddress
Specifies a network IP address as a CIM object.
To obtain an IP address object, use the Get-NetIPAddress cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByIPAddress
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AssociatedNeighbor
Specifies a network neighbor as a CIM object.
To obtain a neighbor object, use the Get-NetNeighbor cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByNeighbor
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AssociatedRoute
Specifies a network route as a CIM object.
To obtain a route object, use the Get-NetRoute cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByRoute
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AutomaticMetric
Specifies an array of values for the automatic metric calculation.
Automatic metric determines whether TCP/IP automatically calculates a value for an interface metric that is based on the speed of the interface.
The fastest interface has the lowest interface metric value.
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

```yaml
Type: AutomaticMetric[]
Parameter Sets: ByName
Aliases: 
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BaseReachableTimeMs
Specifies an array of base values of random reachable times, in milliseconds.
For more information, see [RFC 2461](https://go.microsoft.com/fwlink/p/?LinkId=84044).
The default value is 30000.

```yaml
Type: UInt32[]
Parameter Sets: ByName
Aliases: BaseReachableTime

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

### -ClampMss
Specifies an array of MSS clamping values for IP interface.
This value determines if the IP interface clamps MSS on the forwarded TCP packets that are sent out of the interface.
The acceptable values for this parameter are:

- Enabled
- Disabled

```yaml
Type: ClampMss[]
Parameter Sets: ByName
Aliases: 
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CompartmentId
Specifies an array of identifiers for network compartments in the protocol stack.
By default, the cmdlet only gets Net IP interfaces in the default compartment.
If you specify a value, the cmdlet gets any matching NetIPInterface in all compartments in this field.

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

### -ConnectionState
Specifies an array of connection states for interfaces that are physically connected to a network.

```yaml
Type: ConnectionState[]
Parameter Sets: ByName
Aliases: 
Accepted values: Disconnected, Connected

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CurrentHopLimit
Specifies an array of hop limits.
This parameter is the value that the IP interface writes in the hop limit for IPv6, or the Time To Live (TTL) field, for IPv4, in all outbound traffic.
When forwarding a packet, routers must decrement the hop limit, or TTL, by 1, and discard the packet when the hop limit reaches 0.

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

### -DadRetransmitTimeMs
Specifies an array of values for the time interval between neighbor solicitation messages.

```yaml
Type: UInt32[]
Parameter Sets: ByName
Aliases: DadRetransmitTime

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DadTransmits
Specifies an array of values for the number of consecutive messages sent while the network driver performs duplicate address detection.

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

### -Dhcp
Specifies the DHCP value for an IP interface.
This value is persistent across reboots and only stored in the active policy store. 
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

The default value is Enabled.

```yaml
Type: Dhcp[]
Parameter Sets: ByName
Aliases: 
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DirectedMacWolPattern
Specifies an array of values for the wake-up packet for an IP interface.
This parameter determines if an IP interface is configured to wake up a computer with directed MAC packet patterns.
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

 The default value is Disabled.

```yaml
Type: DirectedMacWolPattern[]
Parameter Sets: ByName
Aliases: 
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EcnMarking
Specifies an array of values for Explicit Congestion Notification (ECN) marking.
This parameter value controls the specific ECN marking in the ECN field of the IP header.
The acceptable values for this parameter are:


 -- AppDecide.
Allow an application or higher layer protocol, such as TCP, to decide how to apply ECN marking.
In order for an application to fully control ECN capability value in the Network TCP value must also be set to enabled. 
 -- Disabled.
Disable the ECN marking on the IP interface. 
 -- UseEct0.
Mark all of the egress IP packets on the IP interface with the Ect0 bit set. 
 -- UseEct1.
Mark all of the egress IP packets on the IP interface with the Ect1 bit set. 


The default value is AppDecide.

```yaml
Type: EcnMarking[]
Parameter Sets: ByName
Aliases: 
Accepted values: Disabled, UseEct1, UseEct0, AppDecide

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceArpNdWolPattern
Specifies an array of Wake On LAN (WOL) values for the IP interface.
This parameter determines if an IP interface is configured to wake up a computer with Address Resolution Protocol (ARP) and Neighbor Discovery (ND) packet patterns.
By default, IP interface properties have *ForceArpNdWolPattern* set to disabled.
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

```yaml
Type: ForceArpNdWolPattern[]
Parameter Sets: ByName
Aliases: 
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Forwarding
Specifies an array of packet forwarding values for the IP interface.
This value determines if this IP interface forwards packets that arrive on this interface to other interfaces.
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

```yaml
Type: Forwarding[]
Parameter Sets: ByName
Aliases: 
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnoreDefaultRoutes
Specifies an array of values for default route advertisements.
If you enable this value, default routes will not be dynamically added to the routing table.
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

The default value is Disabled.

```yaml
Type: IgnoreDefaultRoutes[]
Parameter Sets: ByName
Aliases: 
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeAllCompartments
Indicates that the cmdlet includes all non-default compartments.

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
The cmdlet gets IP interfaces that match the aliases.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: ifAlias

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceIndex
Specifies an array of indexes of network interfaces.
The cmdlet gets IP interfaces that match the indexes.

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
Specifies an array of metrics of IP interfaces.
When routes are chosen, the overall metric used to determine the preference is the sum of the route metric and the interface metric.
Typically, the interface metric gives preference to a particular interface, such as using wired if both wired and wireless are available.
The default value is automatic.

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

### -ManagedAddressConfiguration
Specifies an array of values of managed address configurations.
This parameter determines if an IP interface uses a stateful protocol, such as DHCP, to obtain an address.
Setting this parameter will have no effect on an interface that has router discovery enabled and advertising disabled.
In that case, the parameter is controlled by router discovery.
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

```yaml
Type: ManagedAddressConfiguration[]
Parameter Sets: ByName
Aliases: 
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NeighborDiscoverySupported
Specifies an array of neighbor discovery values for the IP interface.
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

```yaml
Type: NeighborDiscoverySupported[]
Parameter Sets: ByName
Aliases: 
Accepted values: No, Yes

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NeighborUnreachabilityDetection
Specifies an array of values for Neighbor Unreachability Detection (NUD).
Use this parameter to determine when a neighbor is no longer reachable.
For more information, see [RFC 2461](https://go.microsoft.com/fwlink/p/?LinkId=84044).
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

```yaml
Type: NeighborUnreachabilityDetection[]
Parameter Sets: ByName
Aliases: 
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NlMtuBytes
Specifies an array of network layer Maximum Transmission Unit (MTU) values, in bytes, for an IP interface.
The IP interface will not transmit packets larger than the maximum value.

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

### -OtherStatefulConfiguration
Specifies an array of values for configuration other than addresses.
This parameter determines if an IP interface uses a stateful protocol, such as DHCP, to obtain configuration information other than addresses.
This parameter value has no effect on an interface that has router discovery enabled and advertising disabled.
In that case, the parameter is controlled by router discovery.
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

```yaml
Type: OtherStatefulConfiguration[]
Parameter Sets: ByName
Aliases: 
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyStore
Specifies a **PolicyStore** value.
The acceptable values for this parameter are:

 -- ActiveStore.
The IP address information is valid. 
 -- PersistentStore.
The computer saves IP address information across restarts.
When the computer restarts, it copies the saved settings to the ActiveStore. 

The default value is ActiveStore.

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

### -ReachableTimeMs
Specifies an array of reachable time values.
This parameter is the time, in milliseconds, that a node assumes that a neighbor is reachable after having received a reachability confirmation.
This parameter works with the *NeighborUnreachabilityDetection* parameter.

```yaml
Type: UInt32[]
Parameter Sets: ByName
Aliases: ReachableTime

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetransmitTimeMs
Specifies an array of value for timeout and retransmission, in milliseconds, for Neighbor Solicitation messages.
For more information, see RetransTimer in [RFC 2461](https://go.microsoft.com/fwlink/p/?LinkId=84044).
By default, the value is 1000.

```yaml
Type: UInt32[]
Parameter Sets: ByName
Aliases: RetransmitTime

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RouterDiscovery
Specifies the value for router discovery for an IP interface.
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled
 -- ControlledByDHCP.
IP Interface properties for interfaces that have RouterDiscovery controlled by Dynamic Host Configuration Protocol (DHCP). 

By default, the value of this parameter is ControlledByDHCP for IPv4 and Enabled for IPv6.
If the value of this parameter is enabled, an IP host can locate routers that reside on an attached link.

```yaml
Type: RouterDiscovery[]
Parameter Sets: ByName
Aliases: 
Accepted values: Disabled, Enabled, ControlledByDHCP

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

### -WeakHostReceive
Specifies the receive value for a weak host model.
By default, an IP interface properties set this parameter to disabled.
If this parameter is enabled, an IP host can receive IP packets on an interface that is not assigned the destination IP address of the packet being received.
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

```yaml
Type: WeakHostReceive[]
Parameter Sets: ByName
Aliases: 
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WeakHostSend
Specifies the send value for a weak host model.
By default, an IP interface set this parameter to disabled.
If this parameter is enabled, an IP host can send IP packets on an interface that is not assigned the destination IP address of the packet being sent.
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

```yaml
Type: WeakHostSend[]
Parameter Sets: ByName
Aliases: 
Accepted values: Disabled, Enabled

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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIPInterface
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-NetRoute](./Get-NetRoute.md)

[Set-NetIPInterface](./Set-NetIPInterface.md)

