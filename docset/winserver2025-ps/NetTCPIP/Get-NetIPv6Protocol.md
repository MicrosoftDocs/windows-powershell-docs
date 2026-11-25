---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetIPv6Protocol.cdxml-help.xml
Module Name: NetTCPIP
ms.date: 06/23/2021
online version: https://learn.microsoft.com/powershell/module/nettcpip/get-netipv6protocol?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetIPv6Protocol
---

# Get-NetIPv6Protocol

## SYNOPSIS
Gets IPv6 protocol configurations.

## SYNTAX

```
Get-NetIPv6Protocol [-DefaultHopLimit <UInt32[]>] [-NeighborCacheLimitEntries <UInt32[]>]
 [-RouteCacheLimitEntries <UInt32[]>] [-ReassemblyLimitBytes <UInt32[]>] [-IcmpRedirects <IcmpRedirects[]>]
 [-SourceRoutingBehavior <SourceRoutingBehavior[]>] [-DhcpMediaSense <DhcpMediaSense[]>]
 [-MediaSenseEventLog <MediaSenseEventLog[]>] [-MldLevel <MldLevel[]>] [-MldVersion <MldVersion[]>]
 [-MulticastForwarding <MulticastForwarding[]>] [-GroupForwardedFragments <GroupForwardedFragments[]>]
 [-RandomizeIdentifiers <RandomizeIdentifiers[]>] [-AddressMaskReply <AddressMaskReply[]>]
 [-DeadGatewayDetection <DeadGatewayDetection[]>] [-UseTemporaryAddresses <UseTemporaryAddresses[]>] [-MaxTemporaryDadAttempts <UInt32[]>]
 [-MaxTemporaryValidLifetime <TimeSpan[]>] [-MaxTemporaryPreferredLifetime <TimeSpan[]>]
 [-TemporaryRegenerateTime <TimeSpan[]>] [-MaxTemporaryDesyncTime <TimeSpan[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetIPv6Protocol** cmdlet gets the global IPv6 protocol configurations for the computer.
The cmdlet returns IPv6 Protocol settings, such as the Internet Control Message Protocol (ICMP) setting, the default hop limit, the neighbor cache limit, and the multicast configuration.
If you do not specify any parameters, the cmdlet gets all the IPv6 Protocol configuration settings.

## EXAMPLES

### Example 1: Get all IPv6 protocol configurations
```
PS C:\>Get-NetIPv6Protocol
```

This command gets all IPv6 protocol configurations for the IP interface.
The default output for the cmdlet does not include all properties of the **NetIPv6Protocol** object.

### Example 2: Output all properties of IPv6 protocol configurations
```
PS C:\>Get-NetIPv6Protocol | Format-List -Property *
```

This command gets all IPv6 protocol configurations for the IP interface.
The command uses the Format-List cmdlet to display all the properties in the output in the form of a table.
For more information, type `Get-Help Format-Table`.
The command default output omits some properties.

## PARAMETERS

### -AddressMaskReply
Specifies an array of values for address mask reply.
The cmdlet gets the IPv6 protocol configurations that have these values.
Address mask reply specifies how the computer responds to ICMP address mask packets.
The acceptable values for this parameter are:

- Enabled.
The computer responds to ICMP address mask packets.
- Disabled.
The computer does not respond to ICMP address mask packets.

```yaml
Type: AddressMaskReply[]
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

### -DeadGatewayDetection
Specifies an array of values for dead gateway detection. The cmdlet gets IPv6 protocol
configurations that have these values.
Dead gateway detection is a feature that identifies gateways that are not operating properly and
switches the computer to a new default gateway if available.
The acceptable values for this parameter are:

- Enabled
- Disabled

```yaml
Type: DeadGatewayDetection[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultHopLimit
Specifies an array of values for the default hop limit.
The cmdlet gets the IPv6 protocol configurations that have these values.
The default hop limit is the default value for the **CurrentHopLimit** property in the IP interface.
The current hop limit is the value that the IP interface writes in the time-to-live (TTL) field in all outbound traffic.
When routers forward a packet, they decrement the hop limit by 1 and discard the packet when the hop limit is 0.

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
Specifies an array of values for Media Sense.
The cmdlet gets IPv6 protocol configurations that have these values.

Media Sense provides a mechanism for the network adapter to notify the protocol stack of media connect and disconnect events.
These events trigger the DHCP client to take an action, such as attempting to renew a DHCP lease or removing routes that are related to a disconnected network.
When Media Sense is enabled, the network parameters on the laptop of a roaming user are automatically and transparently updated without requiring a restart when the user moves from one location to another.
The acceptable values for this parameter are:

- Enabled
- Disabled

```yaml
Type: DhcpMediaSense[]
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupForwardedFragments
Specifies an array of values for group forwarded fragments.
The cmdlet gets IPv6 protocol configurations that have these values.
Group forwarded fragments specifies whether the IP interface collects fragments into groups before it forwards the fragments.
The acceptable values for this parameter are:

- Enabled.
The IP interface collects IPv4 protocol fragments into groups before it forwards the fragments.
- Disabled.
The IP interface does not collect IPv4 protocol fragments into groups before it forwards the fragments.

```yaml
Type: GroupForwardedFragments[]
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IcmpRedirects
Specifies an array of values for ICMP redirects.
The cmdlet gets IPv4 protocol configurations that have these values.
ICMP redirects specifies whether to update the path cache in response to ICMP redirect packets.
The acceptable values for this parameter are:

- Enabled.
The IP interface updates the path cache in response to ICMP redirect packets.
- Disabled.
The IP interface does not update the path cache in response to ICMP redirect packets.

```yaml
Type: IcmpRedirects[]
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxTemporaryDadAttempts
Specifies an array of values for the maximum number of duplicate address detection attempts for temporary addresses.
The cmdlet gets IPv6 protocol configurations that have these values.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases: MaxDadAttempts

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxTemporaryDesyncTime
Specifies an array of values for the maximum time to desynchronize temporary address preferred lifetimes.
The cmdlet gets IPv6 protocol configurations that have these values.

```yaml
Type: TimeSpan[]
Parameter Sets: (All)
Aliases: MaxRandomTime

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxTemporaryPreferredLifetime
Specifies an array of values, as **TimeSpan** objects, for the maximum preferred lifetime over which to prefer a temporary address.
The cmdlet gets IPv6 protocol configurations that have these values.

```yaml
Type: TimeSpan[]
Parameter Sets: (All)
Aliases: MaxPreferredLifetime

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxTemporaryValidLifetime
Specifies an array of values, as **TimeSpan** objects, for the maximum lifetime over which a temporary address is valid.
The cmdlet gets IPv6 protocol configurations that have these values.

```yaml
Type: TimeSpan[]
Parameter Sets: (All)
Aliases: MaxValidLifetime

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MediaSenseEventLog
Specifies an array of values for Media Sense event log.
The cmdlet gets IPv6 protocol configurations that have these values.
Media Sense event log specifies whether the computer logs DHCP Media Sense events.
The acceptable values for this parameter are:

- Enabled.
The IP interface logs DHCP Media Sense events in the event log for troubleshooting purposes.
- Disabled.
The IP interface does not log DHCP Media Sense events in the event log.

```yaml
Type: MediaSenseEventLog[]
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MldLevel
Specifies an array of values for the level of Multicast Listener Discovery (MLD) support.
The cmdlet gets IPv6 protocol configurations that have these values.
The acceptable values for this parameter are:

- All.
The computer can send and receive multicast packets.
- None.
The computer cannot send or receive multicast packets.
- SendOnly.
The computer can send but not receive multicast packets.

```yaml
Type: MldLevel[]
Parameter Sets: (All)
Aliases:
Accepted values: None, SendOnly, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MldVersion
Specifies an array of values for the maximum version of Multicast Listener Discovery that the host supports.
The cmdlet gets IPv6 protocol configurations that have these values.

```yaml
Type: MldVersion[]
Parameter Sets: (All)
Aliases:
Accepted values: Version1, Version2

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MulticastForwarding
Specifies an array of values for multicast forwarding.
The cmdlet gets IPv6 protocol configurations that have these values.
The acceptable values for this parameter are:

- Enabled.
The computer can forward multicast packets.
- Disabled.
The computer cannot forward multicast packets.

```yaml
Type: MulticastForwarding[]
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NeighborCacheLimitEntries
Specifies an array of values for the maximum number of neighbor cache entries.
The cmdlet gets IPv6 protocol configurations that have these values.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases: NeighborCacheLimit

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RandomizeIdentifiers
Specifies an array of values for the randomization of identifiers.
The cmdlet gets IPv6 protocol configurations that have these values.
The acceptable values for this parameter are:

- Enabled.
The IP interface randomizes identifiers when it creates an IP address.
- Disabled: The IP interface does not randomize identifiers when it creates an IP address.

```yaml
Type: RandomizeIdentifiers[]
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReassemblyLimitBytes
Specifies an array of values for the maximum size of the reassembly buffer.
The cmdlet gets IPv6 protocol configurations that have these values.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases: ReassemblyLimit

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RouteCacheLimitEntries
Specifies an array of values for the maximum number of route cache entries.
The cmdlet gets IPv6 protocol configurations that have these values.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases: RouteCacheLimit

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceRoutingBehavior
Specifies an array of values for the behavior for source-routed packets.
The cmdlet gets IPv6 protocol configurations that have these values.
The acceptable values for this parameter are:

- DontForward.
The computer can receive but not forward source-routed packets.
- Drop.
The computer drops source-routed packets.

```yaml
Type: SourceRoutingBehavior[]
Parameter Sets: (All)
Aliases:
Accepted values: Forward, DontForward, Drop

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemporaryRegenerateTime
Specifies an array of values, as **TimeSpan** objects, for the time before deprecating a temporary address when a new address is generated.

The cmdlet gets IPv6 protocol configurations that have these values.

```yaml
Type: TimeSpan[]
Parameter Sets: (All)
Aliases: RegenerateTime

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell&reg; calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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
Specifies an array of values for temporary addresses.
The cmdlet gets IPv6 protocol configurations that have these values.
The acceptable values for this parameter are:

- Always.
The computer always generates temporary addresses by using random numbers.
- Counter.
The computer generates temporary addresses by using the interface identifier.
You typically use this identifier for test purposes.
- Disabled.
The computer does not use temporary addresses.
- Enabled.
The computer uses temporary addresses.

```yaml
Type: UseTemporaryAddresses[]
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled, Always

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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIPv6Protocol
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Set-NetIPv6Protocol](./Set-NetIPv6Protocol.md)

[Get-NetIPv4Protocol](./Get-NetIPv4Protocol.md)

