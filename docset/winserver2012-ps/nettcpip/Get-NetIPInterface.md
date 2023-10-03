---
external help file: NetTCPIP_Cmdlets.xml
Module Name: NetTCPIP
online version: https://learn.microsoft.com/powershell/module/nettcpip/get-netipinterface?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NetIPInterface

## SYNOPSIS
Gets information about the IP interface properties.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-NetIPInterface [[-InterfaceAlias] <String[]>] [-AddressFamily <AddressFamily[]>]
 [-AdvertiseDefaultRoute <AdvertiseDefaultRoute[]>] [-AdvertisedRouterLifetime <TimeSpan[]>]
 [-Advertising <Advertising[]>] [-AsJob] [-AutomaticMetric <AutomaticMetric[]>]
 [-BaseReachableTimeMs <UInt32[]>] [-CimSession <CimSession[]>] [-ConnectionState <ConnectionState[]>]
 [-CurrentHopLimit <UInt32[]>] [-DadTransmits <UInt32[]>] [-Dhcp <Dhcp[]>]
 [-DirectedMacWolPattern <DirectedMacWolPattern[]>] [-EcnMarking <EcnMarking[]>]
 [-ForceArpNdWolPattern <ForceArpNdWolPattern[]>] [-Forwarding <Forwarding[]>]
 [-IgnoreDefaultRoutes <IgnoreDefaultRoutes[]>] [-InterfaceIndex <UInt32[]>] [-InterfaceMetric <UInt32[]>]
 [-ManagedAddressConfiguration <ManagedAddressConfiguration[]>]
 [-NeighborDiscoverySupported <NeighborDiscoverySupported[]>]
 [-NeighborUnreachabilityDetection <NeighborUnreachabilityDetection[]>] [-NlMtuBytes <UInt32[]>]
 [-OtherStatefulConfiguration <OtherStatefulConfiguration[]>] [-PolicyStore <String>]
 [-ReachableTimeMs <UInt32[]>] [-RetransmitTimeMs <UInt32[]>] [-RouterDiscovery <RouterDiscovery[]>]
 [-ThrottleLimit <Int32>] [-WeakHostReceive <WeakHostReceive[]>] [-WeakHostSend <WeakHostSend[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-NetIPInterface [-AsJob] [-AssociatedRoute <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-NetIPInterface [-AsJob] [-AssociatedNeighbor <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_4
```
Get-NetIPInterface [-AsJob] [-AssociatedAdapter <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_5
```
Get-NetIPInterface [-AsJob] [-AssociatedIPAddress <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-NetIPInterface** cmdlet gets IP interface properties such as IPv4 addresses, IPv6 addresses and the IP interfaces to which these addresses are associated.
Interface properties include properties such as DHCP is enabled or disabled, Wake on LAN (WoL) settings and IPv6 address auto-configuration settings.
More information on IPv6 is available here IPv6 Address Autoconfiguration on TechNethttp://technet.microsoft.com/library/cc778502(WS.10).aspx. 

This cmdlet does not get the gateway as that is a routing concept covered by the Get-NetRoute cmdlet.
For IP endpoints, the gateway specifies the forwarding or next hop IP address over which the set of addresses defined by the network destination and subnet mask are reachable. 

Without parameters, this cmdlet gets all of the IP interface properties on the computer, including virtual interfaces and loopback interfaces.

## EXAMPLES

### EXAMPLE 1
```
Used without parameters gets IP interface information for the computer.
PS C:\>Get-NetIPInterface


The default output omits some properties. Use this cmdlet to display all fields (all properties of the object).
PS C:\>Get-NetIPAddress | Format-List -Property *
```

This example gets information about IP interface configuration.

### EXAMPLE 2
```
PS C:\>Get-NetIPInterface -AddressFamily IPv6
```

This example gets information about IP interface configuration for all IP interfaces that have IPv6 addresses configured.

### EXAMPLE 3
```
PS C:\>Get-NetIPInterface | Format-Table
```

This example gets information about IP interface configuration, and it displays some of that information in a table. 

The table format provides a convenient overview for computers with many IP interfaces.

### EXAMPLE 4
```
PS C:\>Get-NetIPInterface -InterfaceIndex 12
```

This example gets information about IP interface configuration for a specific InterfaceIndex.

### EXAMPLE 5
```
PS C:\>Get-NetIPInterface | Sort-Object -Property InterfaceIndex | Format-Table
```

This example gets information about IP address configuration, sorts them numerically by the interface index in the cmdlet name, and then displays them in a table format.
This display can help you find IP address information by interface index.

### EXAMPLE 6
```
PS C:\>Get-NetIPInterface | Where-Object -FilterScript { $_.AdvertisedRouterLifetime.TotalSeconds -Eq 1800 }
```

This example gets information about IP address configuration for all IP interfaces that have a default AdvertisedRouterLifetime.

## PARAMETERS

### -AddressFamily
Gets IP interface properties only about interfaces that have IP addresses of a specific IP address family.
The acceptable values for this parameter are:

 -- IPv4: IP Interface properties for interfaces with IPv4 addresses. 

 -- IPv6: IP Interface properties for interfaces with IPv6 addresses.

```yaml
Type: AddressFamily[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdvertiseDefaultRoute
Gets IP interface properties only for interfaces by AdvertiseDefaultRoute.
This parameter indicates whether the IP interface should advertise itself as a default router regardless of whether the node has a default route itself.
Valid only for advertising interfaces.
The acceptable values for this parameter are:

 -- Enabled: IP Interface properties for interfaces with the AdvertiseDefaultRoute set to Enabled. 

 -- Disabled: IP Interface properties for interfaces with the AdvertiseDefaultRoute set to Disabled.

```yaml
Type: AdvertiseDefaultRoute[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdvertisedRouterLifetime
Gets IP interface properties only for interfaces by AdvertisedRouterLifetime.
This parameter indicates the lifetime of default routes when advertising routes on the IP interface, in seconds.
The default value is 1800.
Valid only for advertising interfaces.
This parameter uses time as defined by the TimeSpanhttp://msdn.microsoft.com/library/system.timespan.aspx structure.

```yaml
Type: TimeSpan[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Advertising
Gets IP interface properties only for interfaces by if they send or do not send Router Advertisements.
The default value is Disabled.
The acceptable values for this parameter are:

 -- Enabled: IP Interface properties for interfaces that are enabled to send Router Advertisements. 

 -- Disabled: IP Interface properties for interfaces that have Router Advertisements disabled.

```yaml
Type: Advertising[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### -AssociatedAdapter
Gets IP interface properties only about a specific network adapter CIM object.
This is typically as input through the pipeline.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AssociatedIPAddress
Gets IP interface properties only about a specific network IP address CIM object.
This is typically as input through the pipeline.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AssociatedNeighbor
Gets IP interface properties only about a specific network neighbor CIM object.
This is typically as input through the pipeline.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AssociatedRoute
Gets IP interface properties only about a specific network route CIM object.
This is typically as input through the pipeline.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AutomaticMetric
Gets IP interface properties only for interfaces by the AutomaticMetric property.
This parameter determines whether TCP/IP automatically calculates a value for an interface metric that is based on the speed of the interface.
The highest-speed interface has the lowest interface metric value.
The acceptable values for this parameter are:

 -- Enabled: IP Interface properties for interfaces with the AutomaticMetric set to Enabled. 

 -- Disabled: IP Interface properties for interfaces with the AutomaticMetric set to Disabled.

```yaml
Type: AutomaticMetric[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BaseReachableTimeMs
Gets IP interface properties only for interfaces by the BaseReachableTime property.
This parameter is the base for random reachable time, in milliseconds.
This parameter is described in [RFC 2461](https://go.microsoft.com/fwlink/p/?LinkId=84044).
The default BaseReachableTime setting is `30000`.

```yaml
Type: UInt32[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### -ConnectionState
Gets IP interface properties only for interfaces that are physically connected to a network.

```yaml
Type: ConnectionState[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CurrentHopLimit
Gets IP interface properties only for interfaces that have a specific CurrentHopLimit.
This parameter is the value that the IP interface writes in the hop limit (for IPv6) or TTL (for IPv4) field in all outbound traffic.
When forwarding a packet, routers are required to decrease the Hop Limit or TTL by 1 and to discard the packet when the Hop Limit or TTL is 0.
The default is defined as DefaultHopLimit in the NetIPv4Protocol and NetIPv6Protocol objects.
When CurrentHopLimit is set to 0, it uses this default.

```yaml
Type: UInt32[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DadTransmits
Gets IP interface properties only for interfaces that have a specific DadTransmits property.
This parameter is the number of duplicate address detection transmits.

```yaml
Type: UInt32[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Dhcp
Gets the enabled state for the IP interface of the Dynamic Host Configuration Protocol (DHCP). 
Note: This setting is persistent across reboots and only stored in the active policy store. 
The acceptable values for this parameter are:

 -- Enabled: IP Interface properties for interfaces that have DHCP enabled. 

 -- Disabled: IP Interface properties for interfaces that have DHCP disabled. 

The default value is Enabled.

```yaml
Type: Dhcp[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DirectedMacWolPattern
Gets IP interface properties only for interfaces by if they have DirectedMacWolPattern enabled or disabled.
DirectedMacWolPattern determines if an IP interface is configured to wake up a computer with directed MAC packet patterns.
By default, IP interface properties have DirectedMacWolPattern set to disabled.
The acceptable values for this parameter are:

 -- Enabled: IP Interface properties for interfaces that have DirectedMacWolPattern enabled. 

 -- Disabled: IP Interface properties for interfaces that have DirectedMacWolPattern disabled.

```yaml
Type: DirectedMacWolPattern[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EcnMarking
Gets one or more IP interface properties only for interfaces with a specific ECN marking value.
This parameter value controls the specific ECN marking in the ECN field of the IP header.
The acceptable values for this parameter are:

 -- AppDecide: Allow an application or higher layer such as TCP to decide how to apply ECN marking.
In order for an application to fully control ECN capability value in the Network TCP setting must also be set to Enabled. 

 -- Disabled: Disable the ECN marking on the IP interface. 

 -- UseEct0: Mark all of the egress IP packets on the IP interface with the Ect0 bit set. 

 -- UseEct1: Mark all of the egress IP packets on the IP interface with the Ect1 bit set. 

The default value is AppDecide.

```yaml
Type: EcnMarking[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceArpNdWolPattern
Gets IP interface properties only for interfaces by if they have ForceArpNdWolPattern enabled or disabled.
This parameter determines if an IP interface is configured to wake up a computer with Address Resolution Protocol (ARP) and Neighbor Discovery (ND) packet patterns.
By default, IP interface properties have ForceArpNdWolPattern set to disabled.
The acceptable values for this parameter are:

 -- Enabled: IP Interface properties for interfaces that have ForceArpNdWolPattern enabled. 

 -- Disabled: IP Interface properties for interfaces that have ForceArpNdWolPattern disabled.

```yaml
Type: ForceArpNdWolPattern[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Forwarding
Gets IP interface properties only about a specific interface, as defined by Forwarding.
Forwarding determines whether packets arriving on this IP interface can be forwarded to other interfaces.
The acceptable values for this parameter are:

 -- Enabled: IP Interface properties for interfaces that have Forwarding enabled. 

 -- Disabled: IP Interface properties for interfaces that have Forwarding disabled.

```yaml
Type: Forwarding[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnoreDefaultRoutes
Gets IP interface properties only about a specific interface, as defined by IgnoreDefaultRoutes.
If enabled, then IgnoreDefaultRoutes ensures that default routes will not be dynamically added to the routing table.
By default, interface properties have IgnoreDefaultRoutes set to disabled.
The acceptable values for this parameter are:

 -- Enabled: IP Interface properties for interfaces that have IgnoreDefaultRoutes enabled. 

 -- Disabled: IP Interface properties for interfaces that have IgnoreDefaultRoutes disabled.

```yaml
Type: IgnoreDefaultRoutes[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: Disabled
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterfaceAlias
Gets IP interface properties only about a specific interface, as defined by the InterfaceAlias.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceIndex
Gets IP interface properties only about a specific interface, as defined by the InterfaceIndex number.

```yaml
Type: UInt32[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceMetric
Gets IP interface properties only about a specific interface, as defined by the InterfaceMetric.
When routes are chosen, the overall metric used to determine the preference is the sum of the route metric and the interface metric.
Typically, the interface metric gives preference to a particular interface, such as using wired if both wired and wireless are available.
The default value is automatic.

```yaml
Type: UInt32[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedAddressConfiguration
Gets IP interface properties only for interfaces by the ManagedAddressConfiguration property.
This parameter determines if an IP interface uses a stateful protocol (such as DHCP) to obtain an address.
Setting this parameter will have no effect on an interface that has router discovery enabled and advertising disabled.
In that case the parameter is controlled by router discovery.
The acceptable values for this parameter are:

 -- Enabled: IP Interface properties for interfaces that have ManagedAddressConfiguration enabled. 

 -- Disabled: IP Interface properties for interfaces that have ManagedAddressConfiguration disabled.

```yaml
Type: ManagedAddressConfiguration[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NeighborDiscoverySupported
Gets IP interface properties only for interfaces by the NeighborDiscoverySupported property.
This parameter specifies if the IP interface supports neighbor discovery.
The acceptable values for this parameter are:

 -- Enabled: IP Interface properties for interfaces that have NeighborDiscoverySupported enabled. 

 -- Disabled: IP Interface properties for interfaces that have NeighborDiscoverySupported disabled.

```yaml
Type: NeighborDiscoverySupported[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NeighborUnreachabilityDetection
Gets IP interface properties only for interfaces by the NeighborUnreachablilityDetection property.
This parameter is how nodes determine that a neighbor is no longer reachable.
Default depends on type of interface.
This parameter is described in RFC 2461http://go.microsoft.com/fwlink/p/?LinkId=84044.
The acceptable values for this parameter are:

 -- Enabled: IP Interface properties for interfaces that have NeighborUnreachabilityDetection enabled. 

 -- Disabled: IP Interface properties for interfaces that have NeighborUnreachabilityDetection disabled.

```yaml
Type: NeighborUnreachabilityDetection[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NlMtuBytes
Gets IP interface properties only about a specific interface, as defined by the Network Layer MTU (NlMtu) property.
NlMtu is the network layer Maximum Transmission Unit, in bytes.
The IP interface will not transmit packets larger than NlMtuBytes.

```yaml
Type: UInt32[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OtherStatefulConfiguration
Gets IP interface properties only for interfaces by if they have a specific OtherStateful setting.
OtherStateful determines if an IP interface uses a stateful protocol (such as DHCP) to obtain configuration information other than addresses.
Setting this parameter will have no effect on an interface that has router discovery enabled and advertising disabled.
In that case the parameter is controlled by router discovery.
The acceptable values for this parameter are:

 -- Enabled: IP Interface properties for interfaces that have OtherStatefulConfiguration enabled. 

 -- Disabled: IP Interface properties for interfaces that have OtherStatefulConfiguration disabled.

```yaml
Type: OtherStatefulConfiguration[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReachableTimeMs
Gets IP interface properties only about a specific interface, as defined by the BaseReachableTime.
This parameter is the time, in milliseconds, that a node assumes that a neighbor is reachable after having received a reachability confirmation.
Used by Neighbor Unreachability Detection.

```yaml
Type: UInt32[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetransmitTimeMs
Gets IP interface properties only about a specific interface, as defined by the RetransmitTime.
This parameter defines the timeout and retransmission of Neighbor Solicitation messages, in milliseconds.
This parameter is described as RetransTimer in RFC 2461http://go.microsoft.com/fwlink/p/?LinkId=84044.
The default value is `1000`.

```yaml
Type: UInt32[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RouterDiscovery
Gets IP interface properties only for interfaces by if they have a specific RouterDiscovery setting.
By default, interface properties have RouterDiscovery ControlledByDHCP for IPv4 and enabled for IPv6.
If RouterDiscovery is enabled, then an IP host can locate routers that reside on an attached link.
The acceptable values for this parameter are:

 -- Enabled: IP Interface properties for interfaces that have RouterDiscovery enabled. 

 -- Disabled: IP Interface properties for interfaces that have RouterDiscovery disabled. 

 -- ControlledByDHCP: IP Interface properties for interfaces that have RouterDiscovery controlled by Dynamic Host Configuration Protocol (DHCP).

```yaml
Type: RouterDiscovery[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### -WeakHostReceive
Gets IP interface properties only for interfaces by if they have WeakHostReceive enabled or disabled.
By default, interface properties have WeakHostReceive set to disabled.
If WeakHostReceive is enabled, then an IP host can receive IP packets on an interface that is not assigned the destination IP address of the packet being received.
The acceptable values for this parameter are:

 -- Enabled: IP Interface properties for interfaces that have WeakHostReceive enabled. 

 -- Disabled: IP Interface properties for interfaces that have WeakHostReceive disabled.

```yaml
Type: WeakHostReceive[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WeakHostSend
Gets IP interface properties only for interfaces by if they have WeakHostSend enabled or disabled.
By default, interface properties have WeakHostSend set to disabled.
If WeakHostSend is enabled, then an IP host can send IP packets on an interface that is not assigned the destination IP address of the packet being sent.
The acceptable values for this parameter are:

 -- Enabled: IP Interface properties for interfaces that have WeakHostSend enabled. 

 -- Disabled: IP Interface properties for interfaces that have WeakHostSend disabled.

```yaml
Type: WeakHostSend[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIPInterface
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Format-List](https://go.microsoft.com/fwlink/p/?LinkId=113302)

[Format-Table](https://go.microsoft.com/fwlink/p/?LinkId=113303)

[Sort-Object](https://go.microsoft.com/fwlink/p/?LinkId=113403)

[Where-Object](https://go.microsoft.com/fwlink/p/?LinkId=113423)

[Get-NetRoute](./Get-NetRoute.md)

[Set-NetIPInterface](./Set-NetIPInterface.md)

