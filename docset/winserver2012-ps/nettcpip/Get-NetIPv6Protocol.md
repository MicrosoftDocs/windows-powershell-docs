---
external help file: NetTCPIP_Cmdlets.xml
Module Name: NetTCPIP
online version: https://docs.microsoft.com/powershell/module/nettcpip/get-netipv6protocol?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NetIPv6Protocol

## SYNOPSIS
Gets information about the IPv6 protocol configuration.

## SYNTAX

```
Get-NetIPv6Protocol [-AddressMaskReply <AddressMaskReply[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-DefaultHopLimit <UInt32[]>] [-DhcpMediaSense <DhcpMediaSense[]>]
 [-GroupForwardedFragments <GroupForwardedFragments[]>] [-IcmpRedirects <IcmpRedirects[]>]
 [-MaxDadAttempts <UInt32[]>] [-MaxPreferredLifetime <TimeSpan[]>] [-MaxRandomTime <TimeSpan[]>]
 [-MaxValidLifetime <TimeSpan[]>] [-MediaSenseEventLog <MediaSenseEventLog[]>] [-MldLevel <MldLevel[]>]
 [-MldVersion <MldVersion[]>] [-MulticastForwarding <MulticastForwarding[]>]
 [-NeighborCacheLimitEntries <UInt32[]>] [-RandomizeIdentifiers <RandomizeIdentifiers[]>]
 [-ReassemblyLimitBytes <UInt32[]>] [-RegenerateTime <TimeSpan[]>] [-RouteCacheLimitEntries <UInt32[]>]
 [-SourceRoutingBehavior <SourceRoutingBehavior[]>] [-ThrottleLimit <Int32>]
 [-UseTemporaryAddresses <UseTemporaryAddresses[]>]
```

## DESCRIPTION
The **Get-NetIPv6Protocol** cmdlet gets the global IPv6 protocol configuration for the computer.
This includes parameters such as the default hop limit, the neighbor cache limit, and multicast configuration.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NetIPv6Protocol


The default output omits some properties. Run the cmdlet to display all fields (all properties of the object).
PS C:\>Get-NetIPv6Protocol | Format-List -Property *
```

This example gets information about IPv6 protocol configuration.

## PARAMETERS

### -AddressMaskReply
Gets IPv6 protocol configuration by the AddressMaskReply.
AddressMaskReply indicates whether the computer will respond to ICMP Address mask packets.
The acceptable values for this parameter are:

 -- Enabled: IPv6 protocol configuration that contains the AddressMaskReply set to Enabled. 

 -- Disabled: IPv6 protocol configuration that contains the AddressMaskReply set to Disabled.

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
Gets IPv6 protocol configuration by the DefaultHopLimit.
DefaultHopLimit sets the default value for the CurrentHopLimit property in NetIPInterface.
The CurrentHopLimit is the value that the IP interface writes in the hop limit field in all outbound IPv6 traffic.
When forwarding a packet, routers are required to decrease the Hop Limit by 1 and to discard the packet when the Hop Limit is 0. 

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
Gets IPv6 protocol configuration by the DHCPMediaSense.
DHCP Media Sense provides a mechanism for the network interface card (NIC) to notify the protocol stack of media connect and disconnect events.
These events trigger the DHCP client to take some action, such as attempting to renew a DHCP lease or removing routes related to a disconnected network.
One use of Media Sense enables the network parameters on the notebook computer of a roaming user to automatically and transparently update without rebooting when the user moves from one location to another.
The acceptable values for this parameter are:

 -- Enabled: IPv6 protocol configuration that contains the DhcpMediaSense set to Enabled. 

 -- Disabled: IPv6 protocol configuration that contains the DhcpMediaSense set to Disabled. 

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
Gets IPv6 protocol configuration by the GroupForwardedFragments.
GroupForwardedFragments determines whether fragments should be collected into groups before being forwarded.
The acceptable values for this parameter are:

 -- Enabled: IPv6 protocol configuration that contains the GroupForwardedFragments set to Enabled. 

 -- Disabled: IPv6 protocol configuration that contains the GroupForwardedFragments set to Disabled. 

The default value is Disabled.

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

### -IcmpRedirects
Gets IPv6 protocol configuration by the IcmpRedirects.
IcmpRedirects determine whether the path cache is updated in response to ICMP redirect packets.
The acceptable values for this parameter are:

 -- Enabled: IPv6 protocol configuration that contains the IcmpRedirects set to Enabled. 

 -- Disabled: IPv6 protocol configuration that contains the IcmpRedirects set to Disabled. 

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

### -MaxDadAttempts
Gets IPv6 protocol configuration by the number of MaxDadAttempts.
MaxDadAttempts determines the number of duplicate address detection attempts.
The default value is `5`.

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

### -MaxPreferredLifetime
Gets IPv6 protocol configuration by MaxPreferredLifetime.
MaxPreferredLifetime determines the maximum lifetime over which a temporary address is preferred.
MaxPreferredLifetime uses time as defined by the TimeSpanhttps://msdn.microsoft.com/library/system.timespan.aspx structure. 

The default value is 1 day.

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

### -MaxRandomTime
Gets IPv6 protocol configuration by MaxRandomTime.
MaxRandomTime determines the upper bound to use when computing a random delay at startup time.
MaxRandomTime uses time as defined by the TimeSpanhttps://msdn.microsoft.com/library/system.timespan.aspx structure. 

The default value is 10 minutes.

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

### -MaxValidLifetime
Gets IPv6 protocol configuration by MaxValidLifetime.
MaxValidLifetime determines the Maximum lifetime over which a temporary address is valid.
MaxValidLifetime uses time as defined by the TimeSpanhttps://msdn.microsoft.com/library/system.timespan.aspx structure. 

The default value is 7 days.

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

### -MediaSenseEventLog
Gets IPv6 protocol configuration by the MediaSenseEventLog.
MediaSenseEventLog determines if the computer logs DHCP Media Sense events. 

When enabled, Media Sense events (connection/disconnection from the network) are logged in the event log for troubleshooting purposes.
The acceptable values for this parameter are:

 -- Enabled: IPv6 protocol configuration that contains the MediaSenseEventLog set to Enabled. 

 -- Disabled: IPv6 protocol configuration that contains the MediaSenseEventLog set to Disabled. 

The default value is Disabled.

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

### -MldLevel
Gets IPv6 protocol configuration by the MLDLevel. 
MLDLevel determines the level of multicast support.
MLDLevel may determine (None) that multicast packets can neither be sent nor received; (SendOnly) the multicast packets can be sent but not received; or (All) multicast packets can be sent and received.
The acceptable values for this parameter are:

 -- None: IPv6 protocol configuration that contains the MLDLevel set to None. 

 -- SendOnly: IPv6 protocol configuration that contains the MLDLevel set to SendOnly. 

 -- All: IPv6 protocol configuration that contains the MLDLevel set to All. 

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

### -MldVersion
Gets IPv6 protocol configuration by the MLDVersion number.
The MLDVersion shows the maximum MLD version supported by the host.

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

### -MulticastForwarding
Gets IPv6 protocol configuration by the MulticastForwarding.
MulticastForwarding determines whether multicast packets can be forwarded.
The acceptable values for this parameter are:

 -- Enabled: IPv6 protocol configuration that contains the MulticastForwarding set to Enabled. 

 -- Disabled: IPv6 protocol configuration that contains the MulticastForwarding set to Disabled. 

The default value is Disabled.

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
Gets IPv6 protocol configuration by the number of NeighborCacheLimitEntries.
NeighborCacheLimitEntries determines the maximum number of neighbor cache entries. 

The default is 256.

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
Gets IPv6 protocol configuration by the RandomizeIdentifiers. 
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
Gets IPv6 protocol configuration by ReassemblyLimitBytes.
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

### -RegenerateTime
Gets IPv6 protocol configuration by RegenerateTime.
RegenerateTime determines Time prior to deprecating a temporary address when a new address is generated.
RegenerateTime uses time as defined by the TimeSpanhttps://msdn.microsoft.com/library/system.timespan.aspx structure. 

The default value is 5 seconds.

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

### -RouteCacheLimitEntries
Gets IPv6 protocol configuration by the number of RouteCacheLimitEntries.
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
Gets IPv6 protocol configuration by the SourceRoutingBehavior.
SourceRoutingBehavior determines the behavior for source routed packets.
(DontForward) source routed packets can be received but not forwarded. 
DontForward is the default setting.
(Drop) source routed packets will be dropped.
(Forward) Per RFC 5095https://www.ietf.org/rfc/rfc5095.txt support for forwarding of source routed IPv6 packets has been removed, and the Forward setting now has the same effect as DontForward.
The acceptable values for this parameter are:

 -- DontForward: IPv6 protocol configuration that contains the SourceRoutingBehavior set to DontForward. 

 -- Drop: IPv6 protocol configuration that contains the SourceRoutingBehavior set to Drop.

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

### -UseTemporaryAddresses
Gets IPv6 protocol configuration by the UseTemporaryAddresses.
UseTemporaryAddresses determines whether temporary addresses are enabled.
Temporary addresses are described in RFC 3041https://www.ietf.org/rfc/rfc3041.txt.
UseTemporary address may be set to (Disabled) don't use temporary addresses; (Enabled) use temporary addresses; (Always) Always generate random numbers; (Counter) Generate temporary addresses with the interface identifier.
The acceptable values for this parameter are:

 -- Disabled: IPv6 protocol configuration that contains the UseTemporaryAddresses set to Disabled. 

 -- Enabled: IPv6 protocol configuration that contains the UseTemporaryAddresses set to Enabled. 

 -- Always: IPv6 protocol configuration that contains the UseTemporaryAddresses set to Always. 

 -- Counter: IPv6 protocol configuration that contains the UseTemporaryAddresses set to Counter.
Typically used for test purposes.

```yaml
Type: UseTemporaryAddresses[]
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIPv6Protocol
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Format-List](https://go.microsoft.com/fwlink/p/?LinkId=113302)

[Get-NetIPv4Protocol](./Get-NetIPv4Protocol.md)

