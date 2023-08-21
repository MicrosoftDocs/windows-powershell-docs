---
external help file: NetTCPIP_Cmdlets.xml
Module Name: NetTCPIP
online version: https://learn.microsoft.com/powershell/module/nettcpip/set-netipinterface?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NetIPInterface

## SYNOPSIS
Modifies IP interface properties.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NetIPInterface [[-InterfaceAlias] <String[]>] [-AddressFamily <AddressFamily[]>]
 [-AdvertiseDefaultRoute <AdvertiseDefaultRoute>] [-AdvertisedRouterLifetime <TimeSpan>]
 [-Advertising <Advertising>] [-AsJob] [-AutomaticMetric <AutomaticMetric>] [-BaseReachableTimeMs <UInt32>]
 [-CimSession <CimSession[]>] [-CurrentHopLimit <UInt32>] [-DadTransmits <UInt32>] [-Dhcp <Dhcp>]
 [-DirectedMacWolPattern <DirectedMacWolPattern>] [-EcnMarking <EcnMarking>]
 [-ForceArpNdWolPattern <ForceArpNdWolPattern>] [-Forwarding <Forwarding>]
 [-IgnoreDefaultRoutes <IgnoreDefaultRoutes>] [-InterfaceIndex <UInt32[]>] [-InterfaceMetric <UInt32>]
 [-ManagedAddressConfiguration <ManagedAddressConfiguration>]
 [-NeighborDiscoverySupported <NeighborDiscoverySupported[]>]
 [-NeighborUnreachabilityDetection <NeighborUnreachabilityDetection>] [-NlMtuBytes <UInt32>]
 [-OtherStatefulConfiguration <OtherStatefulConfiguration>] [-PassThru] [-PolicyStore <String>]
 [-ReachableTime <UInt32[]>] [-RetransmitTimeMs <UInt32>] [-RouterDiscovery <RouterDiscovery>]
 [-ThrottleLimit <Int32>] [-WeakHostReceive <WeakHostReceive>] [-WeakHostSend <WeakHostSend>] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-NetIPInterface [-AdvertiseDefaultRoute <AdvertiseDefaultRoute>] [-AdvertisedRouterLifetime <TimeSpan>]
 [-Advertising <Advertising>] [-AsJob] [-AutomaticMetric <AutomaticMetric>] [-BaseReachableTimeMs <UInt32>]
 [-CimSession <CimSession[]>] [-CurrentHopLimit <UInt32>] [-DadTransmits <UInt32>] [-Dhcp <Dhcp>]
 [-DirectedMacWolPattern <DirectedMacWolPattern>] [-EcnMarking <EcnMarking>]
 [-ForceArpNdWolPattern <ForceArpNdWolPattern>] [-Forwarding <Forwarding>]
 [-IgnoreDefaultRoutes <IgnoreDefaultRoutes>] [-InterfaceMetric <UInt32>]
 [-ManagedAddressConfiguration <ManagedAddressConfiguration>]
 [-NeighborUnreachabilityDetection <NeighborUnreachabilityDetection>] [-NlMtuBytes <UInt32>]
 [-OtherStatefulConfiguration <OtherStatefulConfiguration>] [-PassThru] [-RetransmitTimeMs <UInt32>]
 [-RouterDiscovery <RouterDiscovery>] [-ThrottleLimit <Int32>] [-WeakHostReceive <WeakHostReceive>]
 [-WeakHostSend <WeakHostSend>] -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-NetIPInterface** cmdlet modifies IP interface properties such as is DHCP, IPv6 neighbor discovery settings, router settings and Wake on LAN (WoL) settings.
The NetIPInterface object is automatically created by the computer and thus the NetIPInterface object has no New or Remove verbs.

Without identifier parameters, this cmdlet sets all of the IP interface properties on the computer, including virtual interfaces and loopback interfaces.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-NetIPInterface -InterfaceIndex 12 -Dhcp Disabled
```

This example gets information IP interface object for the InterfaceIndex 12 and disabled DHCP on it.

### EXAMPLE 2
```
PS C:\>Set-NetIPInterface -AddressFamily IPv6
```

This example gets information about IP interface configuration for all of the IP interfaces that have IPv6 addresses configured.

### EXAMPLE 3
```
PS C:\>Get-NetAdapter | Where-Object -FilterScript {$_.LinkSpeed -Eq "100 Mbps"} | Set-NetIPInterface -InterfaceMetric 21
```

This example gets all of the network adapters on the computer with a link speed of 100 Mbps and sets the interface metric on them to 21.

## PARAMETERS

### -AddressFamily
Specifies the IP address family of the IP interface.
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
Modifies the IP interface advertise default route property.
This parameter value indicates whether the IP interface should advertise itself as a default router regardless of whether the node has a default route itself.
Valid only for advertising interfaces.
The acceptable values for this parameter are:

 -- Enabled: The IP interface advertises itself as the default router. 

 -- Disabled: The IP interface does not advertise itself as the default router.

```yaml
Type: AdvertiseDefaultRoute
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdvertisedRouterLifetime
Modifies IP interface advertised router lifetime property.
This parameter value indicates the lifetime of default routes when advertising routes on the IP interface, in seconds.
The default value is `1800`.
Valid only for advertising interfaces.
AdvertisedRouterLifetime uses time as defined by the TimeSpanhttp://msdn.microsoft.com/library/system.timespan.aspx structure.

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

### -Advertising
Modifies IP interface properties only for interfaces that send or do not send Router Advertisements.
By default, interface properties have advertising set to Disabled.
The acceptable values for this parameter are:

 -- Enabled: IP Interface is enabled to send Router Advertisements. 

 -- Disabled: IP Interface has Router Advertisements disabled.

```yaml
Type: Advertising
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

### -AutomaticMetric
Modifies the automatic metric property.
This parameter value determines whether TCP/IP automatically calculates a value for an interface metric that is based on the speed of the interface.
The highest-speed interface has the lowest interface metric value.
The acceptable values for this parameter are:

 -- Enabled: TCP/IP automatically calculates a value for an InterfaceMetric that is based on the speed of the interface. 

 -- Disabled: TCP/IP uses the manual setting for InterfaceMetric.

```yaml
Type: AutomaticMetric
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BaseReachableTimeMs
Modifies the BaseReachableTime property.
BaseReachableTime is the base for random reachable time, in milliseconds.
This parameter is described in RFC 2461http://go.microsoft.com/fwlink/p/?LinkId=84044. 

The default value is 30.

```yaml
Type: UInt32
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

### -CurrentHopLimit
Modifies the current hop limit property.
This parameter value is the value that the IP interface writes in the hop limit (for IPv6) or TTL (for IPv4) field in all outbound traffic.
When forwarding a packet, routers are required to decrease the Hop Limit or TTL by 1 and to discard the packet when the Hop Limit or TTL is 0.
The default is defined as DefaultHopLimit in the NetIPv4Protocol and NetIPv6Protocol objects.
When this parameter value is set to 0, it uses this default.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DadTransmits
Modifies the dad transmits property.
This parameter value is the number of duplicate address detection transmits.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Dhcp
Modifies the enabled state for the IP interface of the Dynamic Host Configuration Protocol (DHCP). 
Note: This setting is persistent across reboots and only stored in the active policy store. 

Changes to the persistent store will have no effect. 
The acceptable values for this parameter are:

 -- Enabled: IP Interface properties for interfaces that have DHCP enabled. 

 -- Disabled: IP Interface properties for interfaces that have DHCP disabled. 

The default value is Enabled.

```yaml
Type: Dhcp
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DirectedMacWolPattern
Modifies the directed MAC WoL pattern.
This parameter value determines if an IP interface is configured to wake up a computer with directed MAC packet patterns.
By default, IP interface properties have this parameter value set to Disabled.
The acceptable values for this parameter are:

 -- Enabled: IP Interface properties for interfaces that have DirectedMacWolPattern enabled. 

 -- Disabled: IP Interface properties for interfaces that have DirectedMacWolPattern disabled.

```yaml
Type: DirectedMacWolPattern
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EcnMarking
Modifies the ECN marking value.
This parameter value controls the specific ECN marking in the ECN field of the IP header.
The acceptable values for this parameter are:

 -- AppDecide: Allow an application or higher layer such as TCP to decide how to apply ECN marking.
In order for an application to fully control ECN capability value in the Network TCP setting must also be set to Enabled. 

 -- Disabled: Disable the ECN marking on the IP interface. 

 -- UseEct0: Mark all of the egress IP packets on the IP interface with the Ect0 bit set. 

 -- UseEct1: Mark all of the egress IP packets on the IP interface with the Ect1 bit set. 

The default value is AppDecide.

```yaml
Type: EcnMarking
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceArpNdWolPattern
Modifies the force ARP ND WoL pattern parameter.
This parameter value determines if an IP interface is configured to wake up a computer with Address Resolution Protocol (ARP) and Neighbor Discovery (ND) packet patterns.
By default, IP interface properties have this parameter value set to Disabled.
The acceptable values for this parameter are:

 -- Enabled: IP Interface properties for interfaces that have ForceArpNdWolPattern enabled. 

 -- Disabled: IP Interface properties for interfaces that have ForceArpNdWolPattern disabled.

```yaml
Type: ForceArpNdWolPattern
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Forwarding
Modifies the forwarding property.
The acceptable values for this parameter are:

 -- Enabled: Packets arriving on this IP interface can be forwarded to other interfaces. 

 -- Disabled: Packets arriving on this IP interface cannot be forwarded to other interfaces.

```yaml
Type: Forwarding
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnoreDefaultRoutes
Modifies the ignore default routes property.
The acceptable values for this parameter are:

 -- Enabled: Ensures that default routes will not be dynamically added to the routing table. 

 -- Disabled: Allows default routes to be dynamically added to the routing table.
This is the default.

```yaml
Type: IgnoreDefaultRoutes
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Disabled
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InterfaceAlias
Specifies the IP interface properties by interface, as defined by the InterfaceAlias property.

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
Specifies the IP interface properties by interface, as defined by the InterfaceIndex number property.

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
Modifies the interface metric property.
When routes are chosen, the overall metric used to determine the preference is the sum of the route metric and the interface metric.
Typically, the interface metric gives preference to a particular interface, such as using wired if both wired and wireless are available.
This parameter value uses the value generated by AutomaticMetric by default.
If this parameter value is set, then AutomaticMetric is automatically disabled.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedAddressConfiguration
Modifies the managed address configuration property.
This parameter value determines if an IP interface uses a stateful protocol (such as DHCP) to obtain an address.
Setting this parameter will have no effect on an interface that has router discovery enabled and advertising disabled.
In that case the parameter is controlled by router discovery.
The acceptable values for this parameter are:

 -- Enabled: The IP interface uses a stateful protocol (such as DHCP) to obtain an address. 

 -- Disabled: The IP interface does not use a stateful protocol (such as DHCP) to obtain an address.

```yaml
Type: ManagedAddressConfiguration
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NeighborDiscoverySupported
Specifies the neighbor discovery supported property of the IP interface.
This parameter value specifies if the IP interface supports neighbor discovery.
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
Modifies the neighbor unreachablility detection (NUD) property.
NUD is how nodes determine that a neighbor is no longer reachable.
Default depends on type of interface.
This parameter is described in RFC 2461http://go.microsoft.com/fwlink/p/?LinkId=84044.
Note For the ActiveStore, the NUD modification is allowed only from Disabled to Enabled state, but modifying NUD from Enabled to Disabled for ActiveStore fails with Invalid Parameter.
For the PersistentStore, the NUD can be modified to either Enabled or Disabled.
But the interface will need to be restarted for the setting to take effect. 
The acceptable values for this parameter are:

 -- Enabled: NeighborUnreachabilityDetection is enabled. 

 -- Disabled: NeighborUnreachabilityDetection is disabled.

```yaml
Type: NeighborUnreachabilityDetection
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NlMtuBytes
Modifies the Network Layer MTU (NlMtu) property.
This parameter value is the network layer Maximum Transmission Unit, in bytes.
For IPv4 the minimum value is 576 bytes.
For IPv6 the minimum is value is 1280 bytes.
For both IPv4 and IPv6, the maximum value is 2^32-1 (4294967295).
Values outside these ranges will not be set.
If this parameter is set to 0, then it will remain unchanged and maintain its current value.
The IP interface will not transmit packets larger than NlMtuBytes.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OtherStatefulConfiguration
Modifies the other stateful property.
This parameter value determines if an IP interface uses a stateful protocol (such as DHCP) to obtain configuration information other than addresses.
Setting this parameter will have no effect on an interface that has router discovery enabled and advertising disabled.
In that case the parameter is controlled by router discovery.
The acceptable values for this parameter are:

 -- Enabled: The IP interface uses a stateful protocol (such as DHCP) to obtain configuration information other than addresses. 

 -- Disabled: The IP Interface does not a stateful protocol (such as DHCP) to obtain configuration information other than addresses.

```yaml
Type: OtherStatefulConfiguration
Parameter Sets: (All)
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

### -ReachableTime
Specifies the base reachable time property of the IP interface.
This parameter value is the time, in milliseconds, that a node assumes that a neighbor is reachable after having received a reachability confirmation.
Used by neighbor unreachability detection.

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
Modifies the retransmit time.
This parameter value defines the timeout and retransmission of Neighbor Solicitation messages, in milliseconds.
This parameter is described as RetransTimer in RFC 2461http://go.microsoft.com/fwlink/p/?LinkId=84044.
The default value is `1000`.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RouterDiscovery
Modifies the router discovery property.
By default, interface properties have router discovery controlled by DHCP for IPv4 and Enabled for IPv6.
The acceptable values for this parameter are:

 -- ControlledByDHCP: DHCP determines if the IP Interface can be used by the computer to locate routers that reside on an attached link. 

 -- Disabled: IP Interface will not be used by the computer to locate routers that reside on an attached link. 

 -- Enabled: IP Interface can be used by the computer to locate routers that reside on an attached link.

```yaml
Type: RouterDiscovery
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
ps_cimcommon_throttlelimit

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
Modifies the weak host receive property.
By default, interface properties have this parameter value set to disabled.
The acceptable values for this parameter are:

 -- Enabled: A computer can receive IP packets on the IP interface that is not assigned the destination IP address of the packet being received. 

 -- Disabled: A computer cannot receive IP packets on the IP interface that is not assigned the destination IP address of the packet being received.

```yaml
Type: WeakHostReceive
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WeakHostSend
Modifies the weak host send property.
By default, interface properties have this parameter value set to disabled.
The acceptable values for this parameter are:

 -- Enabled: A computer can send IP packets on an interface that is not assigned the destination IP address of the packet being sent. 

 -- Disabled: A computer cannot send IP packets on an interface that is not assigned the destination IP address of the packet being sent.

```yaml
Type: WeakHostSend
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIPInterface
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Where-Object](https://go.microsoft.com/fwlink/p/?LinkId=113423)

[Get-NetIPInterface](./Get-NetIPInterface.md)

[Get-NetAdapter](../netadapter/Get-NetAdapter.md)

