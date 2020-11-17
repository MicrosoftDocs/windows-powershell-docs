---
external help file: NetTCPIP_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: BA8D07D8-D2E9-4F20-AB3E-63DD98C0F96B
manager: dansimp
---

# Get-NetIPv4Protocol

## SYNOPSIS
Gets information about the IPv4 Protocol configuration.

## SYNTAX

```
Get-NetIPv4Protocol [-AddressMaskReply <AddressMaskReply[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-DefaultHopLimit <UInt32[]>] [-DhcpMediaSense <DhcpMediaSense[]>]
 [-GroupForwardedFragments <GroupForwardedFragments[]>] [-IcmpRedirects <IcmpRedirects[]>]
 [-IGMPLevel <MldLevel[]>] [-IGMPVersion <MldVersion[]>] [-MediaSenseEventLog <MediaSenseEventLog[]>]
 [-MulticastForwarding <MulticastForwarding[]>] [-NeighborCacheLimitEntries <UInt32[]>]
 [-RandomizeIdentifiers <RandomizeIdentifiers[]>] [-ReassemblyLimitBytes <UInt32[]>]
 [-RouteCacheLimitEntries <UInt32[]>] [-SourceRoutingBehavior <SourceRoutingBehavior[]>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-NetIPv4Protocol** cmdlet gets the global IPv4 protocol configuration for the computer.
This includes parameters such as the default hop limit, the neighbor cache limit, and multicast configuration.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NetIPv4Protocol


The default output omits some properties. Run this cmdlet to display all fields (all properties of the object).
PS C:\>Get-NetIPv4Protocol | Format-List -Property *
```

This example gets information about IPv4 protocol configuration.

## PARAMETERS

### -AddressMaskReply
Gets IPv4 protocol configuration by the AddressMaskReply.
AddressMaskReply indicates whether the computer will respond to ICMP Address mask packets.
The acceptable values for this parameter are:

 -- Enabled: IPv4 protocol configuration that contains the AddressMaskReply set to Enabled. 

 -- Disabled: IPv4 protocol configuration that contains the AddressMaskReply set to Disabled.

```yaml
Type: AddressMaskReply[]
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

### -DefaultHopLimit
Gets IPv4 protocol configuration by the DefaultHopLimit.
DefaultHopLimit sets the default value for the CurrentHopLimit property in NetIPInterface.
The CurrentHopLimit is the value that the IP interface writes in the TTL (Time to live) field in all outbound traffic.
When forwarding a packet, routers are required to decrease the TTL by 1 and to discard the packet when the TTL is 0. 

The default value is 128.

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

### -DhcpMediaSense
Gets IPv4 protocol configuration by the DHCPMediaSense.
DHCP Media Sense provides a mechanism for the network interface card (NIC) to notify the protocol stack of media connect and disconnect events.
These events trigger the DHCP client to take some action, such as attempting to renew a DHCP lease or removing routes related to a disconnected network.
One application of Media Sense enables the network parameters on the notebook computer of a roaming user to automatically and transparently update without rebooting when the user moves from one location to another.
The acceptable values for this parameter are:

 -- Enabled: IPv4 protocol configuration that contains the DhcpMediaSense set to Enabled. 

 -- Disabled: IPv4 protocol configuration that contains the DhcpMediaSense set to Disabled. 

The default value is Enabled.

```yaml
Type: DhcpMediaSense[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupForwardedFragments
Gets IPv4 protocol configuration by the GroupForwardedFragments.
GroupForwardedFragments determines whether fragments should be collected into groups before being forwarded.
The acceptable values for this parameter are:

 -- Enabled: IPv4 protocol configuration that contains the GroupForwardedFragments set to Enabled. 

 -- Disabled: IPv4 protocol configuration that contains the GroupForwardedFragments set to Disabled. 

The default value is disabled.

```yaml
Type: GroupForwardedFragments[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IGMPLevel
Gets IPv4 protocol configuration by the IGMPLevel.
IGMPLevel determines the level of multicast support.
IGMPLevel may determine (None) that multicast packets can neither be sent nor received; (SendOnly) the multicast packets can be sent but not received; or (All) multicast packets can be sent and received.
The acceptable values for this parameter are:

 -- None: IPv4 protocol configuration that contains the IGMPLevel set to None. 

 -- SendOnly: IPv4 protocol configuration that contains the IGMPLevel set to SendOnly. 

 -- All: IPv4 protocol configuration that contains the IGMPLevel set to All. 

The default value is All.

```yaml
Type: MldLevel[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IGMPVersion
Gets IPv4 protocol configuration by the IGMPVersion number.
The IGMPVersion shows the maximum IGMP version supported by the host.

```yaml
Type: MldVersion[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IcmpRedirects
Gets IPv4 protocol configuration by the IcmpRedirects.
IcmpRedirects determine whether the path cache is updated in response to ICMP redirect packets.
The acceptable values for this parameter are:

 -- Enabled: IPv4 protocol configuration that contains the IcmpRedirects set to Enabled. 

 -- Disabled: IPv4 protocol configuration that contains the IcmpRedirects set to Disabled. 

The default value is Enabled.

```yaml
Type: IcmpRedirects[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MediaSenseEventLog
Gets IPv4 protocol configuration by the MediaSenseEventLog.
MediaSenseEventLog determines if the computer logs DHCP Media Sense events. 

When Enabled, Media Sense events (connection/disconnection from the network) are logged in the event log for troubleshooting purposes. 
The acceptable values for this parameter are:

 -- Enabled: IPv4 protocol configuration that contains the MediaSenseEventLog set to Enabled. 

 -- Disabled: IPv4 protocol configuration that contains the MediaSenseEventLog set to Disabled. 

The default is Disabled.

```yaml
Type: MediaSenseEventLog[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MulticastForwarding
Gets IPv4 protocol configuration by the MulticastForwarding.
MulticastForwarding determines whether multicast packets can be forwarded. 
The acceptable values for this parameter are:

 -- Enabled: IPv4 protocol configuration that contains the MulticastForwarding set to Enabled. 

 -- Disabled: IPv4 protocol configuration that contains the MulticastForwarding set to Disabled. 

The default is Disabled.

```yaml
Type: MulticastForwarding[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NeighborCacheLimitEntries
Gets IPv4 protocol configuration by the number of NeighborCacheLimitEntries.
NeighborCacheLimitEntries determines the maximum number of neighbor cache entries.
The default value is `256`.

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

### -RandomizeIdentifiers
Gets IPv4 protocol configuration by the RandomizeIdentifiers. 
RandomizeIdentifiers determines whether interface identifiers are randomized.
The acceptable values for this parameter are:

 -- Enabled: IPv4 protocol configuration that contains the RandomizeIdentifiers set to Enabled. 

 -- Disabled: IPv4 protocol configuration that contains the RandomizeIdentifiers set to Disabled. 

The default is Enabled.

```yaml
Type: RandomizeIdentifiers[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReassemblyLimitBytes
Gets IPv4 protocol configuration by ReassemblyLimitBytes.
ReassemblyLimitBytes determines the maximum size of the reassembly buffer.

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

### -RouteCacheLimitEntries
Gets IPv4 protocol configuration by the number of RouteCacheLimitEntries.
RouteCacheLimitEntries determines the maximum number of route cache entries. 

The default value is 128.

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

### -SourceRoutingBehavior
Gets IPv4 protocol configuration by the SourceRoutingBehavior.
SourceRoutingBehavior determines the behavior for source routed packets.
(DontForward) source routed packets can be received but not forwarded.
(Drop) source routed packets will be dropped.
(Forward) Per RFC 5095http://www.ietf.org/rfc/rfc5095.txt support for forwarding of source routed IPv6 packets has been removed, and the Forward setting now has the same effect as DontForward.
The acceptable values for this parameter are:

 -- DontForward: IPv4 protocol configuration that contains the SourceRoutingBehavior set to DontForward. 

 -- Drop: IPv4 protocol configuration that contains the SourceRoutingBehavior set to Drop. 

The default value is DontForward.

```yaml
Type: SourceRoutingBehavior[]
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

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIPv4Protocol
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Format-Table](https://go.microsoft.com/fwlink/p/?LinkId=113303)

[Get-NetIPv6Protocol](./Get-NetIPv6Protocol.md)

