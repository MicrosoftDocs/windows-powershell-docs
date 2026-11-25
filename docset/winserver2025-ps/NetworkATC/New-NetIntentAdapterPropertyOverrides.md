---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 03/14/2025
online version: https://learn.microsoft.com/powershell/module/networkatc/new-netintentadapterpropertyoverrides?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetIntentAdapterPropertyOverrides
---

# New-NetIntentAdapterPropertyOverrides

## SYNOPSIS
Creates a new instance of network adapter property overrides which can be used to supply granular values to `Set-NetIntent`.

## SYNTAX

```
New-NetIntentAdapterPropertyOverrides [-EncapOverhead <Int32>]
 [-EncapsulatedPacketTaskOffload <Int32>] [-EncapsulatedPacketTaskOffloadNvgre <Int32>]
 [-EncapsulatedPacketTaskOffloadVxlan <Int32>] [-FlowControl <Int32>] [-InterruptModeration <Int32>]
 [-IPChecksumOffloadIPv4 <Int32>] [-JumboPacket <Int32>] [-LsoV2IPv4 <Int32>] [-LsoV2IPv6 <Int32>]
 [-NetworkDirect <Int32>] [-NetworkDirectTechnology <Int32>] [-NumaNodeId <Int32>]
 [-PacketDirect <Int32>] [-PriorityVLANTag <Int32>] [-PtpHardwareTimestamp <Int32>] [-QOS <Int32>]
 [-QosOffload <Int32>] [-ReceiveBuffers <Int32>] [-RscIPv4 <Int32>] [-RscIPv6 <Int32>]
 [-RssOnHostVPorts <Int32>] [-Sriov <Int32>] [-TCPUDPChecksumOffloadIPv4 <Int32>]
 [-TCPUDPChecksumOffloadIPv6 <Int32>] [-UDPChecksumOffloadIPv4 <Int32>]
 [-UDPChecksumOffloadIPv6 <Int32>] [-TransmitBuffers <Int32>] [-UsoIPv4 <Int32>] [-UsoIPv6 <Int32>]
 [-VMQ <Int32>] [-VxlanUDPPortNumber <Int32>] [-VlanID <UInt16>] [<CommonParameters>]
```

## DESCRIPTION

The `New-NetIntentAdapterPropertyOverrides` cmdlet creates a new instance of network adapter
property overrides, which is used to specify granular settings for adapter properties that can be
applied using the `Set-NetIntent` cmdlet. These settings allow administrators to fine-tune network
adapter properties to optimize performance and functionality for specific network intents.

## EXAMPLES

### Example

```powershell
New-NetIntentAdapterPropertyOverrides -EncapOverhead 50 -FlowControl 1 -JumboPacket 9000
```

This example creates a new instance of adapter property override with an encapsulation overhead of
`50` bytes, with flow control enabled, and jumbo packets set to `9000` bytes.

## PARAMETERS

### -EncapOverhead

Specifies the value of the encapsulation overhead.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncapsulatedPacketTaskOffload

Specifies the value of the encapsulated packet task offload.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncapsulatedPacketTaskOffloadNvgre

Specifies the value of the encapsulated packet task offload for NVGRE.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncapsulatedPacketTaskOffloadVxlan

Specifies the value of the encapsulated packet task offload for VXLAN.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -FlowControl

Specifies if flow control is to be used.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterruptModeration

Specifies the interrupt moderation rate.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPChecksumOffloadIPv4

Specifies the IPv4 checksum offload value.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -JumboPacket

Specifies the maximum size for jumbo packets.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -LsoV2IPv4

Specifies the value of large send offload version 2 (LSO V2) for IPv6.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -LsoV2IPv6

Specifies the value of large send offload version 2 (LSO V2) for IPv6.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkDirect

Specifies the Network Direct value.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkDirectTechnology

Specifies the Network Direct technology value.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumaNodeId

Specifies the NUMA node ID to use for the network adapter.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -PacketDirect

Specifies the Packet Direct value.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -PriorityVLANTag

Specifies the priority value of VLAN tagging.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -PtpHardwareTimestamp

Specifies the hardware timestamp for the Precision Time Protocol (PTP).

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -QOS

Specifies the Quality of Service (QoS) value for the network adapter.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -QosOffload

Specifies whether QoS offloading is to be enabled.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReceiveBuffers

Specifies the number of receive buffers to use.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -RscIPv4

Specifies the value of Receive Segment Coalescing (RSC) for IPv4.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -RscIPv6

Specifies the value of Receive Segment Coalescing (RSC) for IPv6.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -RssOnHostVPorts

Specifies the RSS on host virtual ports.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sriov

Specifies the SR-IOV value.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TCPUDPChecksumOffloadIPv4

Specifies the TCP/UDP checksum offload value for IPv4.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TCPUDPChecksumOffloadIPv6

Specifies the TCP/UDP checksum offload value for IPv6.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -UDPChecksumOffloadIPv4

Specifies the UDP checksum offload for IPv4.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -UDPChecksumOffloadIPv6

Specifies the UDP checksum offload for IPv6.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -TransmitBuffers

Specifies the number of transmit buffers to be used.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -UsoIPv4

Specifies the UDP segment offload (USO) for IPv4.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -UsoIPv6

Specifies the UDP segment offload (USO) for IPv6.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMQ

Specifies the Virtual Machine Queue (VMQ) to use.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -VxlanUDPPortNumber

Specifies the UDP port number to use for VXLAN.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -VlanID

Specifies the VLAN ID.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-NetIntentAdapterRssOverrides](New-NetIntentAdapterRssOverrides.md)

[New-NetIntentGlobalClusterOverrides](New-NetIntentGlobalClusterOverrides.md)

[New-NetIntentGlobalProxyOverrides](New-NetIntentGlobalProxyOverrides.md)

[New-NetIntentQoSPolicyOverrides](New-NetIntentQoSPolicyOverrides.md)

[New-NetIntentSiteOverrides](New-NetIntentSiteOverrides.md)

[New-NetIntentStorageOverrides](New-NetIntentStorageOverrides.md)

[New-NetIntentSwitchConfigurationOverrides](New-NetIntentSwitchConfigurationOverrides.md)
