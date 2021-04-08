---
author: Kateyanne
external help file: NetTCPIP_Cmdlets.xml
manager: dansimp
Module Name: NetTCPIP
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/nettcpip/get-netoffloadglobalsetting?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NetOffloadGlobalSetting

## SYNOPSIS
Gets information about the global TCP/IP offload settings.

## SYNTAX

```
Get-NetOffloadGlobalSetting [-AsJob] [-Chimney <ChimneyEnum[]>] [-CimSession <CimSession[]>]
 [-NetworkDirect <EnabledDisabledEnum[]>] [-NetworkDirectAcrossIPSubnets <AllowedBlockedEnum[]>]
 [-PacketCoalescingFilter <EnabledDisabledEnum[]>] [-ReceiveSegmentCoalescing <EnabledDisabledEnum[]>]
 [-ReceiveSideScaling <EnabledDisabledEnum[]>] [-TaskOffload <EnabledDisabledEnum[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-NetOffloadGlobalSetting** cmdlet gets the global TCP/IP offload settings.
This includes properties such as receive side scaling (RSS), receive segment coalescing (RSC), task offload and network direct.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NetOffloadGlobalSetting
```

This example gets information about the global TCP/IP offload settings.

## PARAMETERS

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

### -Chimney
Gets the global TCP/IP offload settings by Chimney.
Chimney determines the TCP Chimney global state on the system.
The acceptable values for this parameter are:

 -- Enabled: Global TCP/IP offload settings that contain Chimney set to Enabled. 

 -- Disabled: Global TCP/IP offload settings that contain Chimney set to Disabled. 

 -- Automatic: Global TCP/IP offload settings that contain Chimney set to Automatic. 

The default value is Disabled.

```yaml
Type: ChimneyEnum[]
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

### -NetworkDirect
Gets the global TCP/IP offload settings by NetworkDirect.
NetworkDirect determines the Network Direct (RDMA) global state on the system.
This is a server only setting.
The acceptable values for this parameter are:

 -- Enabled: Global TCP/IP offload settings that contain NetworkDirect set to Enabled. 

 -- Disabled: Global TCP/IP offload settings that contain NetworkDirect set to Disabled. 

The default value is Enabled.

```yaml
Type: EnabledDisabledEnum[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Disabled
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkDirectAcrossIPSubnets


```yaml
Type: AllowedBlockedEnum[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PacketCoalescingFilter
Gets the global TCP/IP offload settings by PacketCoalescingFilter.
When the computer is not in a power saving state, the Packet Coalescing filter batches delay-tolerant packets (like ARP, Neighbor Solicitations and SSDP) at the network adapter, reducing the number of CPU interrupts.
This is a client only setting.
The acceptable values for this parameter are:

 -- Enabled: Global TCP/IP offload settings that contain PacketCoalescingFilter set to Enabled. 

 -- Disabled: Global TCP/IP offload settings that contain PacketCoalescingFilter set to Disabled. 

The default value is Enabled.

```yaml
Type: EnabledDisabledEnum[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReceiveSegmentCoalescing
Gets the global TCP/IP offload settings by ReceiveSegmentCoalescing.
ReceiveSegmentCoalescing determines the Receive Segment Coalescing (RSC) global state on the system.
An RSC capable network card may parse multiple TCP/IP packets, strip the headers and indicate the TCP payload gathered from the multiple packets in one indication to the TCP/IP stack.
This reduces the per-packet processing overhead.
The acceptable values for this parameter are:

 -- Enabled: Global TCP/IP offload settings that contain ReceiveSegmentCoalescing set to Enabled. 

 -- Disabled: Global TCP/IP offload settings that contain ReceiveSegmentCoalescing set to Disabled. 

The default value is Enabled.

```yaml
Type: EnabledDisabledEnum[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Disabled
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReceiveSideScaling
Gets the global TCP/IP offload settings by ReceiveSideScaling.
ReceiveSideScaling determines the Receive Side Scaling (RSS) global state on the system.
Receive-Side Scaling (RSS) resolves the single-processor bottleneck by allowing the receive side network load from a network adapter to be shared across multiple processors.
The acceptable values for this parameter are:

 -- Enabled: Global TCP/IP offload settings that contain ReceiveSideScaling set to Enabled. 

 -- Disabled: Global TCP/IP offload settings that contain ReceiveSideScaling set to Disabled. 

The default value is Enabled.

```yaml
Type: EnabledDisabledEnum[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Disabled
Accept pipeline input: False
Accept wildcard characters: False
```

### -TaskOffload
Gets the global TCP/IP offload settings by TaskOffload.
Task Offload determines the state of IP checksum offload, IPsec task offload, and Large Send Offload (LSO).
These features reduce the per-packet processing overhead by offloading packet processing such as checksum calculation to the network adapter.
The acceptable values for this parameter are:

 -- Enabled: The global TCP/IP offload settings that contain TaskOffload set to Enabled. 

 -- Disabled: The global TCP/IP offload settings that contain TaskOffload set to Disabled. 

The default value is Enabled.

```yaml
Type: EnabledDisabledEnum[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Enabled
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetOffloadGlobalSetting
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Set-NetOffloadGlobalSetting](./Set-NetOffloadGlobalSetting.md)

