---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetIPInterface.cdxml-help.xml
Module Name: NetTCPIP
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nettcpip/set-netipinterface?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetIPInterface
---

# Set-NetIPInterface

## SYNOPSIS
Modifies an IP interface.

## SYNTAX

### ByName (Default)
```
Set-NetIPInterface [-InterfaceIndex <UInt32[]>] [[-InterfaceAlias] <String[]>]
 [-AddressFamily <AddressFamily[]>] [-ReachableTime <UInt32[]>]
 [-NeighborDiscoverySupported <NeighborDiscoverySupported[]>] [-CompartmentId <UInt32[]>]
 [-PolicyStore <String>] [-IncludeAllCompartments] [-Forwarding <Forwarding>] [-ClampMss <ClampMss>]
 [-Advertising <Advertising>] [-NlMtuBytes <UInt32>] [-InterfaceMetric <UInt32>]
 [-NeighborUnreachabilityDetection <NeighborUnreachabilityDetection>] [-BaseReachableTimeMs <UInt32>]
 [-RetransmitTimeMs <UInt32>] [-DadTransmits <UInt32>] [-DadRetransmitTimeMs <UInt32>]
 [-RouterDiscovery <RouterDiscovery>] [-ManagedAddressConfiguration <ManagedAddressConfiguration>]
 [-OtherStatefulConfiguration <OtherStatefulConfiguration>] [-WeakHostSend <WeakHostSend>]
 [-WeakHostReceive <WeakHostReceive>] [-IgnoreDefaultRoutes <IgnoreDefaultRoutes>]
 [-AdvertisedRouterLifetime <TimeSpan>] [-AdvertiseDefaultRoute <AdvertiseDefaultRoute>]
 [-CurrentHopLimit <UInt32>] [-ForceArpNdWolPattern <ForceArpNdWolPattern>]
 [-DirectedMacWolPattern <DirectedMacWolPattern>] [-EcnMarking <EcnMarking>] [-Dhcp <Dhcp>]
 [-AutomaticMetric <AutomaticMetric>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetIPInterface -InputObject <CimInstance[]> [-Forwarding <Forwarding>] [-ClampMss <ClampMss>]
 [-Advertising <Advertising>] [-NlMtuBytes <UInt32>] [-InterfaceMetric <UInt32>]
 [-NeighborUnreachabilityDetection <NeighborUnreachabilityDetection>] [-BaseReachableTimeMs <UInt32>]
 [-RetransmitTimeMs <UInt32>] [-DadTransmits <UInt32>] [-DadRetransmitTimeMs <UInt32>]
 [-RouterDiscovery <RouterDiscovery>] [-ManagedAddressConfiguration <ManagedAddressConfiguration>]
 [-OtherStatefulConfiguration <OtherStatefulConfiguration>] [-WeakHostSend <WeakHostSend>]
 [-WeakHostReceive <WeakHostReceive>] [-IgnoreDefaultRoutes <IgnoreDefaultRoutes>]
 [-AdvertisedRouterLifetime <TimeSpan>] [-AdvertiseDefaultRoute <AdvertiseDefaultRoute>]
 [-CurrentHopLimit <UInt32>] [-ForceArpNdWolPattern <ForceArpNdWolPattern>]
 [-DirectedMacWolPattern <DirectedMacWolPattern>] [-EcnMarking <EcnMarking>] [-Dhcp <Dhcp>]
 [-AutomaticMetric <AutomaticMetric>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetIPInterface** cmdlet modifies an IP interface, including Dynamic Host Configuration Protocol (DHCP), IPv6 neighbor discovery settings, router settings and Wake On LAN (WOL) settings.

If you do not specify any parameters, this cmdlet sets all of the IP interface properties on the computer, including virtual interfaces and loopback interfaces.

## EXAMPLES

### Example 1: Modify an interface by the index value
```
PS C:\>Set-NetIPInterface -InterfaceIndex 12 -Dhcp Disabled
```

This command modifies an IP interface object by using the interface index value of 12.
The command also disables DHCP on the interface.

### Example 2: Modify the interface metrics
```
PS C:\>Get-NetAdapter | Where-Object -FilterScript {$_.LinkSpeed -Eq "100 Mbps"} | Set-NetIPInterface -InterfaceMetric 21
```

This command modifies all of the network adapters on the computer with a link speed of 100 Mbps and sets the interface metric on them to 21.

## PARAMETERS

### -AddressFamily
Specifies an array of IP address families.
The cmdlet modifies the IP interface that matches the families.
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
Specifies the default router advertisement for an interface.
This parameter value indicates whether the IP interface should advertise itself as a default router regardless of whether the node has a default route itself.
This parameter is valid only for advertising interfaces.
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

```yaml
Type: AdvertiseDefaultRoute
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdvertisedRouterLifetime
Specifies a lifetime, as a **TimeSpan** object, for a default route.
This parameter value indicates the lifetime of default routes when advertising routes on the IP interface.
The default value is 1800.
This parameter is valid only for advertising interfaces.
To obtain a **TimeSpan** object, use the New-TimeSpan cmdlet.

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
Specifies the router advertisement value for the IP interface.
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

 The default value is Disabled.

```yaml
Type: Advertising
Parameter Sets: (All)
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

### -AutomaticMetric
Specifies the value for automatic metric calculation.
Automatic metric determines whether TCP/IP automatically calculates a value for an interface metric that is based on the speed of the interface.
The fastest interface has the lowest interface metric value.
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

```yaml
Type: AutomaticMetric
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BaseReachableTimeMs
Specifies the base value for random reachable time, in milliseconds.
For more information, see [RFC 2461](https://go.microsoft.com/fwlink/p/?LinkId=84044).

The default value is 30.

```yaml
Type: UInt32
Parameter Sets: (All)
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
Specifies the MSS clamping value for the IP interface.
This value determines if this IP interface clamps MSS on the forwarded TCP packets that are sent out of this interface.
The acceptable values for this parameter are:

- Enabled
- Disabled

```yaml
Type: ClampMss
Parameter Sets: (All)
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
By default, the cmdlet only sets Net IP interfaces in the default compartment.
If you specify a value, the cmdlet sets any matching NetIPInterface in all compartments in this field.

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

### -CurrentHopLimit
Specifies a hop limit.
This parameter is the value that the IP interface writes in the hop limit field for IPv6, or the Time To Live (TTL) field for IPv4, in all outbound traffic.
When forwarding a packet, routers decrement the hop limit, or TTL, by 1, and discard the packet when the hop limit reaches 0.
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

### -DadRetransmitTimeMs
Specifies a value for the time interval between neighbor solicitation messages.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: DadRetransmitTime

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DadTransmits
Specifies a value for the number of consecutive messages sent while the network driver performs duplicate address detection.

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
Specifies the Dynamic Host Configuration Protocol (DHCP) value for an IP interface.
This setting is persistent across reboots and only stored in the active policy store.
Changes to the persistent store will have no effect.
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

The default value is Enabled.

```yaml
Type: Dhcp
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DirectedMacWolPattern
Specifies the wake-up packet value for an IP interface.
This parameter value determines if an IP interface is configured to wake up a computer with directed MAC packet patterns.
The acceptable values for this parameter are:


 -- Enabled

 -- Disabled

The default value is Disabled.

```yaml
Type: DirectedMacWolPattern
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EcnMarking
Specifies the value for Explicit Congestion Notification (ECN) marking.
This parameter value controls the specific ECN marking in the ECN field of the IP header.
The acceptable values for this parameter are:


 -- AppDecide.
Allow an application or higher layer protocol, such as TCP, to decide how to apply ECN marking.
In order for an application to fully control ECN capability value in the Network TCP setting must also be set to Enabled.
 -- Disabled.
Disable the ECN marking on the IP interface.
 -- UseEct0.
Mark all of the egress IP packets on the IP interface with the Ect0 bit set.
 -- UseEct1.
Mark all of the egress IP packets on the IP interface with the Ect1 bit set.


The default value is AppDecide.

```yaml
Type: EcnMarking
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, UseEct1, UseEct0, AppDecide

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceArpNdWolPattern
Specifies the Wake On LAN (WOL) value for the IP interface.
This parameter value determines if an IP interface is configured to wake up a computer with Address Resolution Protocol (ARP) or Neighbor Discovery (ND) packet patterns.
The default value is Disabled.
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

```yaml
Type: ForceArpNdWolPattern
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Forwarding
Specifies the packet forwarding value for the IP interface.
This value determines if this IP interface forwards packets that arrive on this interface to other interfaces.
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

```yaml
Type: Forwarding
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnoreDefaultRoutes
Specifies a value for Default Route advertisements.
If you enable this setting, default routes will not be dynamically added to the routing table.
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

The default value is Disabled.

```yaml
Type: IgnoreDefaultRoutes
Parameter Sets: (All)
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
The cmdlet modifies IP interfaces that match the aliases.

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
The cmdlet modifies IP interfaces that match the indexes.

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
Specifies a metric for an IP interface.
When routes are chosen, the overall metric used to determine the preference is the sum of the route metric and the interface metric.
Typically, the interface metric gives preference to a particular interface, such as using wired if both wired and wireless are available.
This parameter value uses the value generated by *AutomaticMetric* by default.
If this parameter value is set, then the *AutomaticMetric* parameter is automatically disabled.

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
Specifies the value for managed address configuration.
This parameter determines if an IP interface uses a stateful protocol, such as DHCP, to obtain an address.
Setting this parameter has no effect on an interface that has router discovery enabled and advertising disabled.
In that case, the parameter is controlled by router discovery.
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

```yaml
Type: ManagedAddressConfiguration
Parameter Sets: (All)
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
Specifies the value for Neighbor Unreachability Detection (NUD).
Use this parameter to determine when a neighbor is no longer reachable.
For more information, see [RFC 2461](https://go.microsoft.com/fwlink/p/?LinkId=84044).
For ActiveStore, you can modify the NUD from Disabled to Enabled, but modifying NUD from Enabled to Disabled for ActiveStore fails with an invalid parameter.
For the PersistentStore, you can modify the NUD to either Enabled or Disabled, but you will have to restart the interface for the setting to take effect.

The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

```yaml
Type: NeighborUnreachabilityDetection
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NlMtuBytes
Specifies the network layer Maximum Transmission Unit (MTU) value, in bytes, for an IP interface.
For IPv4 the minimum value is 576 bytes.
For IPv6 the minimum is value is 1280 bytes.
For both IPv4 and IPv6, the maximum value is 2^32-1 (4294967295).
You cannot set values outside these ranges.
If this parameter is set to 0, then it will remain unchanged and maintain its current value.
The IP interface will not transmit packets larger than the maximum value.

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
Specifies the value for configuration other than addresses.
This parameter determines if an IP interface uses a stateful protocol, such as DHCP, to obtain configuration information other than addresses.
This parameter setting has no effect on an interface that has router discovery enabled and advertising disabled.
In that case, the parameter is controlled by router discovery.
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

```yaml
Type: OtherStatefulConfiguration
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

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
The acceptable values for this parameter are:


 -- ActiveStore.
The IP address information is valid.
 -- PersistentStore.
The computer saves IP address information across restarts.
When the computer restarts, it copies the saved settings to the ActiveStore.

The default value is ActiveStore.
Specify ActiveStore only.

If you do not specify this parameter, the default entries are created in both the ActiveStore and the PersistentStore.

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

### -ReachableTime
Specifies an array of reachable time values.
This parameter is the time, in milliseconds, that a node assumes that a neighbor is reachable after having received a reachability confirmation.
This parameter works with the *NeighborUnreachabilityDetection* parameter.

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

### -RetransmitTimeMs
Specifies a value for timeout and retransmission, in milliseconds, for Neighbor Solicitation messages.
For more information, see RetransTimer in [RFC 2461](https://go.microsoft.com/fwlink/p/?LinkId=84044).
By default, the value is set to 1000.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: RetransmitTime

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RouterDiscovery
Specifies the value for router discovery for an IP interface,  The acceptable values for this parameter are:

 -- ControlledByDHCP.
DHCP determines if the IP Interface can be used by the computer to locate routers that reside on an attached link.
 -- Disabled: IP Interface will not be used by the computer to locate routers that reside on an attached link.
 -- Enabled.
IP Interface can be used by the computer to locate routers that reside on an attached link.

By default, the value of this parameter is ControlledByDHCP for IPv4 and Enabled for IPv6.
If the value of this parameter is enabled, an IP host can locate routers that reside on an attached link.

```yaml
Type: RouterDiscovery
Parameter Sets: (All)
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
By default, interface properties set this parameter to disabled.
If this parameter is enabled, an IP host can receive IP packets on an interface that is not assigned the destination IP address of the packet being received.
The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

```yaml
Type: WeakHostReceive
Parameter Sets: (All)
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
By default, interface properties set this parameter to disabled.
If this parameter is enabled, an IP host can send IP packets on an interface that is not assigned the destination IP address of the packet being sent.The acceptable values for this parameter are:

 -- Enabled
 -- Disabled

```yaml
Type: WeakHostSend
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIPInterface
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-NetAdapter](../netadapter/Get-NetAdapter.md)

[Get-NetIPInterface](./Get-NetIPInterface.md)

