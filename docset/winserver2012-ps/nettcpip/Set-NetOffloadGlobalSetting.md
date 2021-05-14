---
external help file: NetTCPIP_Cmdlets.xml
Module Name: NetTCPIP
online version: https://docs.microsoft.com/powershell/module/nettcpip/set-netoffloadglobalsetting?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NetOffloadGlobalSetting

## SYNOPSIS
Modifies information about the global TCP/IP offload settings.

## SYNTAX

```
Set-NetOffloadGlobalSetting [-AsJob] [-Chimney <ChimneyEnum>] [-CimSession <CimSession[]>]
 [-InputObject <CimInstance[]>] [-NetworkDirect <EnabledDisabledEnum>]
 [-NetworkDirectAcrossIPSubnets <AllowedBlockedEnum>] [-PacketCoalescingFilter <EnabledDisabledEnum>]
 [-PassThru] [-ReceiveSegmentCoalescing <EnabledDisabledEnum>] [-ReceiveSideScaling <EnabledDisabledEnum>]
 [-TaskOffload <EnabledDisabledEnum>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-NetOffloadGlobalSetting** cmdlet modifies the global TCP/IP offload settings.
This includes properties such as receive side scaling (RSS), receive segment coalescing (RSC), task offload and network direct.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-NetOffloadGlobalSetting -ReceiveSegmentCoalescing Enabled
```

This example sets receive segment coalescing to enabled.

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
Modifies the TCP Chimney global state on the computer.
The acceptable values for this parameter are:

 -- Enabled: Chimney offload is enabled. 

 -- Disabled: Chimney offload is disabled. 

 -- Automatic: Chimney offload is automatically used. 

The default value is Disabled.

```yaml
Type: ChimneyEnum
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

### -NetworkDirect
Modifies the Network Direct (RDMA) global state on the computer.
This is a server only setting.
The acceptable values for this parameter are:

 -- Enabled: NetworkDirect is globally enabled. 

 -- Disabled: NetworkDirect is globally disabled. 

The default value is Enabled.

```yaml
Type: EnabledDisabledEnum
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
Type: AllowedBlockedEnum
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PacketCoalescingFilter
Modifies the Packet Coalescing Filter state on the computer.
When the computer is not in a power saving state, the Packet Coalescing filter batches certain delay-tolerant packets (such as ARP, Neighbor Solicitations and SSDP) at the network adapter, reducing the number of CPU interrupts.
This is a client only setting.
The acceptable values for this parameter are:

 -- Enabled: The packet coalescing filter is enabled. 

 -- Disabled: The packet coalescing filter is disabled. 

The default value is Enabled.

```yaml
Type: EnabledDisabledEnum
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

### -ReceiveSegmentCoalescing
Modifies the Receive Segment Coalescing (RSC) global state on the computer.
An RSC capable network card may parse multiple TCP/IP packets, strip the headers and indicate the TCP payload gathered from the multiple packets in one indication to the TCP/IP stack.
This reduces the per-packet processing overhead.
The acceptable values for this parameter are:

 -- Enabled: Enables Receive Segment Coalescing. 

 -- Disabled: Disables Receive Segment Coalescing. 

The default value is Enabled.

```yaml
Type: EnabledDisabledEnum
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Disabled
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReceiveSideScaling
Modifies the Receive Side Scaling (RSS) global state on the computer.
Receive-Side Scaling (RSS) resolves the single-processor bottleneck by allowing the receive side network load from a network adapter to be shared across multiple processors.
The acceptable values for this parameter are:

 -- Enabled: Enables Receive Side Scaling. 

 -- Disabled: Disables Receive Side Scaling. 

The default value is Enabled.

```yaml
Type: EnabledDisabledEnum
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Disabled
Accept pipeline input: False
Accept wildcard characters: False
```

### -TaskOffload
Modifies the global TCP/IP offload settings by TaskOffload.
Task Offload determines the state of IP checksum offload, IPsec task offload, and Large Send Offload (LSO).
These features reduce the per-packet processing overhead by offloading packet processing such as checksum calculation to the network adapter.
A modification setting only takes effect when upon computer reboot or network adapter restart.
The acceptable values for this parameter are:

 -- Enabled: Enables task offload. 

 -- Disabled: Disables task offload. 

The default value is Enabled.

```yaml
Type: EnabledDisabledEnum
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetOffloadGlobalSetting
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-NetOffloadGlobalSetting](./Get-NetOffloadGlobalSetting.md)

