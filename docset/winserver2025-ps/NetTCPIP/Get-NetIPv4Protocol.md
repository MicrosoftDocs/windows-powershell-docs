---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetIPv4Protocol.cdxml-help.xml
Module Name: NetTCPIP
ms.date: 06/23/2021
online version: https://learn.microsoft.com/powershell/module/nettcpip/get-netipv4protocol?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetIPv4Protocol
---

# Get-NetIPv4Protocol

## SYNOPSIS
Gets IPv4 protocol configurations.

## SYNTAX

```
Get-NetIPv4Protocol [-DefaultHopLimit <UInt32[]>] [-NeighborCacheLimitEntries <UInt32[]>]
 [-RouteCacheLimitEntries <UInt32[]>] [-ReassemblyLimitBytes <UInt32[]>] [-IcmpRedirects <IcmpRedirects[]>]
 [-SourceRoutingBehavior <SourceRoutingBehavior[]>] [-DhcpMediaSense <DhcpMediaSense[]>]
 [-MediaSenseEventLog <MediaSenseEventLog[]>] [-IGMPLevel <MldLevel[]>] [-IGMPVersion <MldVersion[]>]
 [-MulticastForwarding <MulticastForwarding[]>] [-GroupForwardedFragments <GroupForwardedFragments[]>]
 [-RandomizeIdentifiers <RandomizeIdentifiers[]>] [-AddressMaskReply <AddressMaskReply[]>]
 [-DeadGatewayDetection <DeadGatewayDetection[]>] [-MinimumMtu <UInt32[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetIPv4Protocol** cmdlet gets the global settings for IPv4 protocol configurations for the computer.
If you do not specify any parameters, the cmdlet gets the IPv4 protocol configuration settings for all network connections for the computer.
The cmdlet returns IPv4 protocol settings, such as the Internet Control Message Protocol (ICMP) setting, the default hop limit, the neighbor cache limit, and the multicast configuration.

## EXAMPLES

### Example 1: Get all IPv4 protocol configurations
```
PS C:\>Get-NetIPv4Protocol
```

This command gets the global settings for all the IPv4 protocol configurations for the computer.
The default output for the cmdlet does not include all properties of the **NetIPv4Protocol** object.

### Example 2: Output all settings for IPv4 protocol configurations
```
PS C:\>Get-NetIPv4Protocol | Format-List -Property *
```

This command gets the global settings for all IPv4 protocol configurations for the computer.
The command uses the Format-List cmdlet to display all the properties in the output in the form of a table.
For more information, type `Get-Help Format-Table`.

## PARAMETERS

### -AddressMaskReply
Specifies an array of values for address mask reply.
The cmdlet gets the IPv4 protocol configurations that have these values.
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
Specifies an array of values for dead gateway detection. The cmdlet gets IPv4 protocol
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
The cmdlet gets the IPv4 protocol configurations that have these values.
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
The cmdlet gets IPv4 protocol configurations that have these values.

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
The cmdlet gets IPv4 protocol configurations that have these values.
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

### -IGMPLevel
Specifies an array of values for the Internet Group Management Protocol (IGMP) level.
The cmdlet gets IPv4 protocol configurations that have these values.
The IGMP level specifies the level of multicast support.
The acceptable values for this parameter are:

- None
- SendOnly
- All

```yaml
Type: MldLevel[]
Parameter Sets: (All)
Aliases: MldLevel
Accepted values: None, SendOnly, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IGMPVersion
Specifies an array of the IGMP version numbers.
The cmdlet gets IPv4 protocol configurations that have these IGMP version numbers.
The IGMP version is the maximum IGMP version supported by the host of IPv4 protocol configuration.

```yaml
Type: MldVersion[]
Parameter Sets: (All)
Aliases: MldVersion
Accepted values: Version1, Version2, Version3

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

### -MediaSenseEventLog
Specifies an array of values for Media Sense event log.
The cmdlet gets IPv4 protocol configurations that have these values.
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

### -MinimumMtu
Specifies an array of values, in bytes, for network layer Maximum Transmission Unit (MTU).
The cmdlet gets settings that have the Mtu values that you specify.

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

### -MulticastForwarding
Specifies an array of values for multicast forwarding.
The cmdlet gets IPv4 protocol configurations that have these values.
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
The cmdlet gets IPv4 protocol configurations that have these values.

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
The cmdlet gets IPv4 protocol configurations that have these values.
The acceptable values for this parameter are:

- Enabled.
The IP interface randomizes identifiers when it creates an IP address.
- Disabled.
The IP interface does not randomize identifiers when it creates an IP address.

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
The cmdlet gets IPv4 protocol configurations that have these values.

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
The cmdlet gets IPv4 protocol configurations that have these values.

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
The cmdlet gets IPv4 protocol configurations that have these values.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIPv4Protocol
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Set-NetIPv4Protocol](./Set-NetIPv4Protocol.md)

[Get-NetIPv6Protocol](./Get-NetIPv6Protocol.md)

