---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetOffloadGlobalSetting.cdxml-help.xml
Module Name: NetTCPIP
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nettcpip/set-netoffloadglobalsetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetOffloadGlobalSetting
---

# Set-NetOffloadGlobalSetting

## SYNOPSIS
Modifies the global TCP/IP offload settings.

## SYNTAX

```
Set-NetOffloadGlobalSetting [-InputObject <CimInstance[]>] [-ReceiveSideScaling <EnabledDisabledEnum>]
 [-ReceiveSegmentCoalescing <EnabledDisabledEnum>] [-Chimney <ChimneyEnum>]
 [-TaskOffload <EnabledDisabledEnum>] [-NetworkDirect <EnabledDisabledEnum>]
 [-NetworkDirectAcrossIPSubnets <AllowedBlockedEnum>] [-PacketCoalescingFilter <EnabledDisabledEnum>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetOffloadGlobalSetting** cmdlet modifies the global TCP/IP offload settings.
The global settings include Receive Side Scaling, Receive Segment Coalescing, task offload, and NetworkDirect properties.

## EXAMPLES

### Example 1: Enable Receive Segment Coalescing
```
PS C:\>Set-NetOffloadGlobalSetting -ReceiveSegmentCoalescing Enabled
```

This command enables Receive Segment Coalescing on the computer.

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

### -Chimney
Specifies the TCP Chimney global state on the computer.
The acceptable values for this parameter are:


- Enabled

- Disabled

- Automatic


The default value is Disabled.

```yaml
Type: ChimneyEnum
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled, Automatic

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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

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
Specifies the NetworkDirect Remote Direct Memory Access (RDMA) value on the computer.
Use this parameter only on servers.
The acceptable values for this parameter are:


- Enabled

- Disabled


The default value is Enabled.

```yaml
Type: EnabledDisabledEnum
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkDirectAcrossIPSubnets
Specifies a value for NetworkDirect connectivity from outside a local IP network.
The acceptable values for this parameter are:

- Allowed
- Blocked

```yaml
Type: AllowedBlockedEnum
Parameter Sets: (All)
Aliases:
Accepted values: Blocked, Allowed

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PacketCoalescingFilter
Specifies the values for the packet-coalescing filter on the computer.
To reduce the number of interrupts that a computer processes, the packet-coalescing filter combines random broadcast and multicast packets, such as Address Resolution Protocol (ARP) requests, Neighbor Discovery messages, and Simple Service Discovery Protocol (SSDP) requests, into a single packet.
Use this parameter only on client computers.
The acceptable values for this parameter are:


- Enabled

- Disabled


The default value is Enabled.

```yaml
Type: EnabledDisabledEnum
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

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
Specifies the Receive Segment Coalescing settings on the computer.
Receive Segment Coalescing parses small packets of data and combines the data into a single packet.
Coalescing small packets into a single packet reduces the overhead that is required to process packets.
The acceptable values for this parameter are:


- Enabled

- Disabled


The default value is Enabled.

```yaml
Type: EnabledDisabledEnum
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReceiveSideScaling
Specifies the Receive Side Scaling settings on the computer.
Receive Side Scaling distributes the network processing load across multiple processor cores.
The acceptable values for this parameter are:


- Enabled

- Disabled


The default value is Enabled.

```yaml
Type: EnabledDisabledEnum
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TaskOffload
Specifies the global TCP/IP task offload settings.
Task offload settings include IP checksum offload, Internet Protocol security (IPsec) task offload, and Large Send Offload.
These features reduce the overhead of per-packet processing by distributing packet processing tasks, such as checksum calculation, to a network adapter.
A modification takes effect after a computer restarts or a network adapter restarts.
The acceptable values for this parameter are:


- Enabled

- Disabled


The default value is Enabled.

```yaml
Type: EnabledDisabledEnum
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetOffloadGlobalSetting
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-NetOffloadGlobalSetting](./Get-NetOffloadGlobalSetting.md)

