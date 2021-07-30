---
external help file: NetTCPIP_Cmdlets.xml
Module Name: NetTCPIP
online version: https://docs.microsoft.com/powershell/module/nettcpip/set-netipv6protocol?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NetIPv6Protocol

## SYNOPSIS
Modifies information about the IPv6 Protocol configuration.

## SYNTAX

```
Set-NetIPv6Protocol [-AddressMaskReply <AddressMaskReply>] [-AsJob] [-CimSession <CimSession[]>]
 [-DefaultHopLimit <UInt32>] [-DhcpMediaSense <DhcpMediaSense>]
 [-GroupForwardedFragments <GroupForwardedFragments>] [-IcmpRedirects <IcmpRedirects>]
 [-InputObject <CimInstance[]>] [-MaxDadAttempts <UInt32>] [-MaxPreferredLifetime <TimeSpan>]
 [-MaxRandomTime <TimeSpan>] [-MaxValidLifetime <TimeSpan>] [-MediaSenseEventLog <MediaSenseEventLog>]
 [-MldLevel <MldLevel>] [-MldVersion <MldVersion>] [-MulticastForwarding <MulticastForwarding>]
 [-NeighborCacheLimitEntries <UInt32>] [-PassThru] [-RandomizeIdentifiers <RandomizeIdentifiers>]
 [-ReassemblyLimitBytes <UInt32>] [-RegenerateTime <TimeSpan>] [-RouteCacheLimitEntries <UInt32>]
 [-SourceRoutingBehavior <SourceRoutingBehavior>] [-ThrottleLimit <Int32>]
 [-UseTemporaryAddresses <UseTemporaryAddresses>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-NetIPv6Protocol** cmdlet modifies the global IPv6 protocol configuration for the computer.
This includes parameters such as the default hop limit, the neighbor cache limit, and multi-cast configuration.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-NetIPv6Protocol -MediaSenseEventLog Enabled
```

This example enabled the DHCP media sense event log.

### EXAMPLE 2
```
PS C:\>Get-NetIPv6Protocol -NeighborCacheLimit 1000
```

This example allows for more neighbors on the subnet, as the default is 256.

## PARAMETERS

### -AddressMaskReply
Modifies the AddressMaskReply property.
The acceptable values for this parameter are:

 -- Enabled: The computer will respond to ICMP Address mask packets. 

 -- Disabled: The computer will not respond to ICMP Address mask packets.

```yaml
Type: AddressMaskReply
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
Modifies the default hop limit.
This parameter value sets the default value for the CurrentHopLimit property in NetIPInterface.
The CurrentHopLimit is the value that the IP interface writes in the hop limit field in all outbound IPv6 traffic.
When forwarding a packet, routers are required to decrease the Hop Limit by 1 and to discard the packet when the Hop Limit is 0. 

The default value is 128.

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

### -DhcpMediaSense
Modifies the DHCPMediaSense property.
This parameter value provides a mechanism for the network adapter to notify the protocol stack of media connect and disconnect events.
These events trigger the DHCP client to take some action, such as attempting to renew a DHCP lease or removing routes related to a disconnected network.
One application of Media Sense enables the network parameters on the notebook computer of a roaming user to automatically and transparently update without rebooting when the user moves from one location to another.
The acceptable values for this parameter are:

 -- Enabled: DhcpMediaSense set to Enabled. 

 -- Disabled: DhcpMediaSense is set to Disabled. 

The default value is Enabled.

```yaml
Type: DhcpMediaSense
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupForwardedFragments
Modifies the GroupForwardedFragments property.
This parameter value determines whether fragments should be collected into groups before being forwarded.
The default value is Disabled.
The acceptable values for this parameter are:

 -- Enabled: IPv6 protocol fragments are collected into groups before being forwarded. 

 -- Disabled: IPv6 protocol fragments are not collected into groups and are forwarded as the fragments are received.

```yaml
Type: GroupForwardedFragments
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IcmpRedirects
Modifies the IcmpRedirects property.
The acceptable values for this parameter are:

 -- Enabled: The path cache is updated in response to ICMP redirect packets. 

 -- Disabled: The path cache is not updated in response to ICMP redirect packets. 

The default value is Enabled.

```yaml
Type: IcmpRedirects
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MaxDadAttempts
Modifies the number of maximum DAD attempts.
This parameter value determines the number of duplicate address detection attempts. 

The default value is 5.

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

### -MaxPreferredLifetime
Modifies the maximum preferred lifetime.
This parameter value determines the maximum lifetime over which a temporary address is preferred.
This parameter value uses time as defined by the TimeSpanhttps://msdn.microsoft.com/library/system.timespan.aspx structure. 

The default value is 1 day.

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

### -MaxRandomTime
Modifies the maximum random time.
This parameter value determines the upper bound to use when computing a random delay at startup time.
This parameter value uses time as defined by the TimeSpanhttps://msdn.microsoft.com/library/system.timespan.aspx structure. 

The default value is 10 minutes.

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

### -MaxValidLifetime
Modifies the maximum valid lifetime.
This parameter value determines the maximum lifetime over which a temporary address is valid.
This parameter value uses time as defined by the TimeSpanhttps://msdn.microsoft.com/library/system.timespan.aspx structure. 

The default value is 7 days.

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

### -MediaSenseEventLog
Modifies the MediaSenseEventLog property.
The acceptable values for this parameter are:

 -- Enabled: DHCP Media Sense events, connection or disconnection from the network, are logged in the event log for troubleshooting purposes. 

 -- Disabled: DHCP Media Sense events are not logged in the event log. 

The default value is Disabled.

```yaml
Type: MediaSenseEventLog
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MldLevel
Modifies the MLD level.
This parameter value determines the level of multi-cast support.
The acceptable values for this parameter are:

 -- All: Multi-cast packets can be sent and received. 

 -- None: Multi-cast packets can neither be sent nor received. 

 -- SendOnly: Multi-cast packets can be sent but not received. 

The default value is All.

```yaml
Type: MldLevel
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MldVersion
Modifies the MLD version number.
This parameter value displays the maximum MLD version supported by the host.

```yaml
Type: MldVersion
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MulticastForwarding
Modifies the multi-cast forwarding property.
The acceptable values for this parameter are:

 -- Enabled: Multi-cast packets can be forwarded. 

 -- Disabled: Multi-cast packets cannot be forwarded. 

The default value is Disabled.

```yaml
Type: MulticastForwarding
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NeighborCacheLimitEntries
Modifies the number of neighbor cache limit entries.
This parameter value determines the maximum number of neighbor cache entries. 

The default value is 256.

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

### -RandomizeIdentifiers
Modifies the RandomizeIdentifiers property.
The acceptable values for this parameter are:

 -- Enabled: Interface identifiers are randomized when creating an IP address. 

 -- Disabled: Interface identifiers are not randomized when creating an IP address. 

The default value is Enabled.

```yaml
Type: RandomizeIdentifiers
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReassemblyLimitBytes
Modifies the ReassemblyLimitBytes property.
This parameter value determines the maximum size of the reassembly buffer.

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

### -RegenerateTime
Modifies the RegenerateTime property.
This parameter value determines time prior to deprecating a temporary address when a new address is generated.
RegenerateTime uses time as defined by the TimeSpanhttps://msdn.microsoft.com/library/system.timespan.aspx structure. 

The default value is 5 seconds.

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

### -RouteCacheLimitEntries
Modifies the number of route cache limit entries.
This parameter value determines the maximum number of route cache entries. 

The default value is 128.

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

### -SourceRoutingBehavior
Modifies the source routing behavior.
This parameter value determines the behavior for source routed packets.
**Note**: The computer allows three possible values.
However, per RFC 5095https://www.ietf.org/rfc/rfc5095.txt support for forwarding of source routed IPv6 packets has been removed, and the Forward setting now has the same effect as DontForward.
The acceptable values for this parameter are:

 -- DontForward: Source routed packets can be received but not forwarded. 

 -- Drop: Source routed packets will be dropped. 

The default value is DontForward.

```yaml
Type: SourceRoutingBehavior
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
Modifies the UseTemporaryAddresses property.
This parameter value determines whether temporary addresses are enabled.
Temporary addresses are described in RFC 3041https://www.ietf.org/rfc/rfc3041.txt.
The acceptable values for this parameter are:

 -- Always: The computer will always generate temporary addresses with random numbers. 

 -- Counter: The computer will generate temporary addresses with the interface identifier.
This is typically used for test purposes. 

 -- Disabled: The computer will not use temporary addresses. 

 -- Enabled: The computer will use temporary addresses.

```yaml
Type: UseTemporaryAddresses
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIPv6Protocol
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Architectural Overview of the TCP/IP Protocol Suite on TechNet](https://technet.microsoft.com/library/bb726993.aspx)

[Get-NetIPv6Protocol](./Get-NetIPv6Protocol.md)

