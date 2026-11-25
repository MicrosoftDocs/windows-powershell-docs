---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetEventPacketCaptureProvider.cdxml-help.xml
Module Name: NetEventPacketCapture
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/neteventpacketcapture/set-neteventpacketcaptureprovider?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetEventPacketCaptureProvider
---

# Set-NetEventPacketCaptureProvider

## SYNOPSIS
Modifies the configuration for a Remote Packet Capture provider.

## SYNTAX

### BySessionName (Default)
```
Set-NetEventPacketCaptureProvider [[-SessionName] <String[]>] [-Level <Byte>] [-MatchAnyKeyword <UInt64>]
 [-MatchAllKeyword <UInt64>] [-CaptureType <CaptureType>] [-MultiLayer <Boolean>]
 [-LinkLayerAddress <String[]>] [-EtherType <UInt16[]>] [-IpAddresses <String[]>] [-IpProtocols <Byte[]>]
 [-TruncationLength <UInt16>] [-VmCaptureDirection <VmCaptureDirection>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BySessionOfTheProvider
```
Set-NetEventPacketCaptureProvider [-AssociatedEventSession <CimInstance>] [-Level <Byte>]
 [-MatchAnyKeyword <UInt64>] [-MatchAllKeyword <UInt64>] [-CaptureType <CaptureType>] [-MultiLayer <Boolean>]
 [-LinkLayerAddress <String[]>] [-EtherType <UInt16[]>] [-IpAddresses <String[]>] [-IpProtocols <Byte[]>]
 [-TruncationLength <UInt16>] [-VmCaptureDirection <VmCaptureDirection>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByTargetOfTheProvider
```
Set-NetEventPacketCaptureProvider [-AssociatedCaptureTarget <CimInstance>] [-Level <Byte>]
 [-MatchAnyKeyword <UInt64>] [-MatchAllKeyword <UInt64>] [-CaptureType <CaptureType>] [-MultiLayer <Boolean>]
 [-LinkLayerAddress <String[]>] [-EtherType <UInt16[]>] [-IpAddresses <String[]>] [-IpProtocols <Byte[]>]
 [-TruncationLength <UInt16>] [-VmCaptureDirection <VmCaptureDirection>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetEventPacketCaptureProvider -InputObject <CimInstance[]> [-Level <Byte>] [-MatchAnyKeyword <UInt64>]
 [-MatchAllKeyword <UInt64>] [-CaptureType <CaptureType>] [-MultiLayer <Boolean>]
 [-LinkLayerAddress <String[]>] [-EtherType <UInt16[]>] [-IpAddresses <String[]>] [-IpProtocols <Byte[]>]
 [-TruncationLength <UInt16>] [-VmCaptureDirection <VmCaptureDirection>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetEventPacketCaptureProvider** cmdlet modifies the configuration for a Remote Packet Capture provider.

## EXAMPLES

### Example 1: Modify a packet capture provider
```
PS C:\>New-NetEventSession -SessionName "Session01"
PS C:\> Add-NetEventProvider -Name "Microsoft-Windows-TCPIP" -SessionName "Session01"
PS C:\> Add-NetEventPacketCaptureProvider -SessionName "Session01"
PS C:\> Set-NetEventPacketCaptureProvider -SessionName "Session01" -IpAddresses 182.168.0.1 -IpProtocol 6
```

This example modifies a packet capture provider.

The first command uses the New-NetEventSession cmdlet to create a new session named Session01.

The second command uses the Add-NetEventProvider cmdlet to add a TCP/IP Net provider to the session.

The third command uses the Add-NetEventPacketCaptureProvider cmdlet to add a packet capture provider to a session named Session01.

The fourth command modifies the packet capture provider settings.

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

### -AssociatedCaptureTarget
Specifies the associated capture target as a CIM object.
The capture target is one of the three following objects:

- **MSFT_NetEventNetworkAdapter**
- **MSFT_NetEventVmNetworkAdapter**
- **MSFT_NetEventVmSwitch**

To obtain a capture target, use the Get-NetEventNetworkAdapter cmdlet, the Get-NetEventVmNetworkAdapter cmdlet, or the Get-NetEventVmSwitch cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByTargetOfTheProvider
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AssociatedEventSession
Specifies the associated network event session, as a CIM object.
To obtain the network event session, use the Get-NetEventSession cmdlet.

```yaml
Type: CimInstance
Parameter Sets: BySessionOfTheProvider
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CaptureType
Specifies whether the packet capture is enabled for physical network adapters, virtual switches, or both.
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

### -IpAddresses
Specifies an array of IP addresses.
The provider logs network traffic that matches the addresses that this cmdlet specifies.
The provider joins multiple addresses by using logical OR.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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
Position: Named
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
Position: Named
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
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MatchAllKeyword
Specifies a bitmask that restricts the events that the provider logs.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MatchAnyKeyword
Specifies keywords as a set of hexadecimal values.
Keywords are flags that you can combine to generate values.
Use a set of hexadecimal values of the keywords instead of the keyword names, and apply a filter to write ETW events for keyword matches.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MultiLayer
Indicates whether the capture should occur at various layers in the stack.
By default, this parameter has a value of $False.

```yaml
Type: Boolean
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

### -SessionName
Specifies an array of names of sessions associated with packet capture providers.

```yaml
Type: String[]
Parameter Sets: BySessionName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Position: Named
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
Position: Named
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

[Add-NetEventPacketCaptureProvider](./Add-NetEventPacketCaptureProvider.md)

[Add-NetEventProvider](./Add-NetEventProvider.md)

[Get-NetEventPacketCaptureProvider](./Get-NetEventPacketCaptureProvider.md)

[New-NetEventSession](./New-NetEventSession.md)

[Remove-NetEventPacketCaptureProvider](./Remove-NetEventPacketCaptureProvider.md)

[Get-NetEventNetworkAdapter](./Get-NetEventNetworkAdapter.md)

[Get-NetEventVmNetworkAdapter](./Get-NetEventVmNetworkAdapter.md)

[Get-NetEventVmSwitch](./Get-NetEventVmSwitch.md)

[Get-NetEventSession](./Get-NetEventSession.md)

