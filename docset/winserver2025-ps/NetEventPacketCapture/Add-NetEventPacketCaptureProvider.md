---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetEventPacketCaptureProvider.cdxml-help.xml
Module Name: NetEventPacketCapture
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/neteventpacketcapture/add-neteventpacketcaptureprovider?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-NetEventPacketCaptureProvider
---

# Add-NetEventPacketCaptureProvider

## SYNOPSIS
Adds a Remote Packet Capture provider.

## SYNTAX

```
Add-NetEventPacketCaptureProvider [-SessionName] <String> [[-Level] <Byte>] [[-MatchAnyKeyword] <UInt64>]
 [[-MatchAllKeyword] <UInt64>] [[-CaptureType] <CaptureType>] [[-MultiLayer] <Boolean>]
 [[-LinkLayerAddress] <String[]>] [[-EtherType] <UInt16[]>] [[-IpAddresses] <String[]>]
 [[-IpProtocols] <Byte[]>] [[-TruncationLength] <UInt16>] [[-VmCaptureDirection] <VmCaptureDirection>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-NetEventPacketCaptureProvider** cmdlet adds a Remote Packet Capture provider.
You can only use one packet capture provider at a time and you must remove an existing provider before you use this cmdlet to add a new provider.
To remove an existing Remote Packet Capture provider, use the Remove-NetEventPacketCaptureProvider cmdlet.

## EXAMPLES

### Example 1: Add a packet capture provider
```
PS C:\>New-NetEventSession -Name "Session01"
PS C:\> Add-NetEventProvider -Name "Microsoft-Windows-TCPIP" -SessionName "Session01"
PS C:\> Add-NetEventPacketCaptureProvider -SessionName "Session01"
```

This example adds a Remote Packet Capture provider to a session.

The first command uses the New-NetEventSession cmdlet to create a new session named Session01.

The second command adds a provider named Microsoft-Windows-TCPIP to the session named Session01 by using the Add-NetEventProvider cmdlet.

The third command adds a packet capture provider to the session.

## PARAMETERS

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

### -CaptureType
Specifies whether the packet capture is enabled for physical network adapters, virtual switches, or both. The acceptable values for this parameter are:
The acceptable values for this parameter are:

- Physical.
Captures packets from physical network adapters.
- Switch.
Captures packets from the virtual machine switch(es) on Hyper-V hosts.
- BothPhysicalAndSwitch.
Captures packets from both the physical network adapters and the virtual machine switch(es).

```yaml
Type: CaptureType
Parameter Sets: (All)
Aliases:
Accepted values: Physical, Switch, BothPhysicalAndSwitch

Required: False
Position: 4
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EtherType
Specifies an array of ether types.
The most common ether types and their values are IPv4 (0800), IPv6 (86DD) and ARP (0806).

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IpAddresses
Specifies an array of IP addresses.
The provider logs network traffic that matches the addresses that this cmdlet specifies.
The provider joins multiple addresses by using logical OR.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IpProtocols
Specifies an array of one or more IP protocols, such as TCP or UDP, on which to filter.
The packet capture provider logs network traffic that matches this filter.

```yaml
Type: Byte[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Level
Specifies the level of Event Tracing for Windows (ETW) events for the provider.
Use the level of detail for the event to filter the events that are logged.
The default value for this parameter is 0x4.
The acceptable values for this parameter are:

- 0x5.
Verbose
- 0x4.
Informational
- 0x3.
Warning
- 0x2.
Error
- 0x1.
Critical
- 0x0.
LogAlways

The provider must log the event if the value of the event is less than or equal to the value of this parameter.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LinkLayerAddress
Specifies an array of link layer, or Media Access Control (MAC), addresses.
The packet capture provider logs network traffic that matches this filter.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MatchAllKeyword
Specifies a bitmask that restricts the events that the provider logs.
Set the **MatchAnyKeyword** parameter value to 0 (zero) to match all keywords.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MatchAnyKeyword
Specifies keywords as a set of hexadecimal values.
Keywords are flags that you can combine to generate values.
Use a set of hexadecimal values of the keywords instead of the keyword names, and apply a filter to write ETW events for keyword matches.
For more information, see [EnableTraceEx2 function](https://msdn.microsoft.com/en-us/library/windows/desktop/dd392305(v=vs.85)) in the Microsoft Developer Network library.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MultiLayer
Indicates whether the capture occurs at various layers of the stack.
By default, this parameter has a value of $False.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SessionName
Specifies the name of the session associated with the packet capture provider.

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

### -TruncationLength
Specifies the display length of each captured packet.
The default size is 128 bytes.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: 10
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VmCaptureDirection
Specifies the direction of network traffic for a virtual machine capture.
The acceptable values for this parameter are:

- Ingress.
Network traffic from a virtual machine to a virtual switch.
- Egress.
Network traffic from a virtual switch to a virtual machine.

```yaml
Type: VmCaptureDirection
Parameter Sets: (All)
Aliases:
Accepted values: Ingress, Egress, IngressAndEgress

Required: False
Position: 11
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-NetEventProvider](./Add-NetEventProvider.md)

[Get-NetEventPacketCaptureProvider](./Get-NetEventPacketCaptureProvider.md)

[New-NetEventSession](./New-NetEventSession.md)

[Remove-NetEventPacketCaptureProvider](./Remove-NetEventPacketCaptureProvider.md)

[Set-NetEventPacketCaptureProvider](./Set-NetEventPacketCaptureProvider.md)

