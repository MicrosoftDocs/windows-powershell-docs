---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetTCPSetting.cdxml-help.xml
Module Name: NetTCPIP
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nettcpip/set-nettcpsetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetTCPSetting
---

# Set-NetTCPSetting

## SYNOPSIS
Modifies a TCP setting.

## SYNTAX

### ByName (Default)
```
Set-NetTCPSetting [[-SettingName] <String[]>] [-MinRtoMs <UInt32>] [-InitialCongestionWindowMss <UInt32>]
 [-CongestionProvider <CongestionProvider>] [-CwndRestart <CwndRestart>] [-DelayedAckTimeoutMs <UInt32>]
 [-DelayedAckFrequency <Byte>] [-MemoryPressureProtection <MemoryPressureProtection>]
 [-AutoTuningLevelLocal <AutoTuningLevelLocal>] [-EcnCapability <EcnCapability>] [-Timestamps <Timestamps>]
 [-InitialRtoMs <UInt32>] [-ScalingHeuristics <ScalingHeuristics>] [-DynamicPortRangeStartPort <UInt16>]
 [-DynamicPortRangeNumberOfPorts <UInt16>] [-AutomaticUseCustom <AutomaticUseCustom>]
 [-NonSackRttResiliency <NonSackRttResiliency>] [-ForceWS <ForceWS>] [-MaxSynRetransmissions <Byte>]
 [-AutoReusePortRangeStartPort <UInt16>] [-AutoReusePortRangeNumberOfPorts <UInt16>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetTCPSetting -InputObject <CimInstance[]> [-MinRtoMs <UInt32>] [-InitialCongestionWindowMss <UInt32>]
 [-CongestionProvider <CongestionProvider>] [-CwndRestart <CwndRestart>] [-DelayedAckTimeoutMs <UInt32>]
 [-DelayedAckFrequency <Byte>] [-MemoryPressureProtection <MemoryPressureProtection>]
 [-AutoTuningLevelLocal <AutoTuningLevelLocal>] [-EcnCapability <EcnCapability>] [-Timestamps <Timestamps>]
 [-InitialRtoMs <UInt32>] [-ScalingHeuristics <ScalingHeuristics>] [-DynamicPortRangeStartPort <UInt16>]
 [-DynamicPortRangeNumberOfPorts <UInt16>] [-AutomaticUseCustom <AutomaticUseCustom>]
 [-NonSackRttResiliency <NonSackRttResiliency>] [-ForceWS <ForceWS>] [-MaxSynRetransmissions <Byte>]
 [-AutoReusePortRangeStartPort <UInt16>] [-AutoReusePortRangeNumberOfPorts <UInt16>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetTCPSetting** cmdlet modifies a TCP setting.
TCP settings are optimized for different network conditions including latency and congestion.
To apply a TCP setting to a port number or destination IP address range, create a transport filter by using the New-NetTransportFilter cmdlet.

**Note:**
>1) You can modify custom and non-custom settings on Windows server 2016 and 2019.
>2) You can modify only custom settings. Internet and Datacenter settings cannot be modified on Windows 2012 or earlier versions.
>3) On Windows 10, the following parameters are read-only and cannot be modified:

> * MinRtoMs
> * InitialCongestionWindowMss
> * AutomaticUseCustom
> * CongestionProvider
> * CwndRestart
> * DelayedAckTimeoutMs

## EXAMPLES

### Example 1: Change the custom TCP setting
```
PS C:\>Set-NetTCPSetting -SettingName "InternetCustom" -CongestionProvider CTCP -InitialCongestionWindowMss 6
```

This command changes the custom TCP setting to have a value of 6 for the initial congestion window and use compound TCP.

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

### -AutoReusePortRangeNumberOfPorts
Specifies the number of ports for the auto-reuse port range, which is a port range used for local ephemeral port selection by outbound TCP connections for which either SO_REUSE_UNICASTPORT has been set on the socket, or for which connect() has been called without calling bind() on the socket.

If you specify 0, the auto-reuse feature is disabled and ephemeral ports are drawn instead from the dynamic port range as specified by *DynamicPortRangeStartPort* and *DynamicPortRangeNumberOfPorts*, even if SO_REUSE_UNICASTPORT is set on a socket.

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

### -AutoReusePortRangeStartPort
Specifies the starting port for the auto-reuse port range.

This parameter sets the starting port to send and receive TCP traffic, which is a port range used for local ephemeral port selection by outbound TCP connections for which either SO_REUSE_UNICASTPORT has been set on the socket, or for which connect() has been called without calling bind() on the socket.

If you specify 0, the auto-reuse feature is disabled and ephemeral ports are drawn instead from the dynamic port range as specified by *DynamicPortRangeStartPort* and *DynamicPortRangeNumberOfPorts*, even if SO_REUSE_UNICASTPORT is set on a socket.

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

### -AutoTuningLevelLocal
Specifies a TCP auto-tuning level for the host computer.
TCP auto-tuning can improve throughput on high throughput, high latency networks.
The acceptable values for this parameter are:

- Disabled.
Sets the TCP receive window to the default value.
- HighlyRestricted.
Sets the TCP receive window to grow beyond the default value, but very conservatively.
- Restricted.
Sets the TCP receive window to grow beyond the default value, but less conservatively than HighlyRestricted.
- Normal.
Sets the TCP receive window to grow to accommodate almost all scenarios.
- Experimental.
Sets the TCP receive window to grow to accommodate extreme scenarios.

```yaml
Type: AutoTuningLevelLocal
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, HighlyRestricted, Restricted, Normal, Experimental

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutomaticUseCustom
Specifies whether the automatic profile assigns a custom template, either Datacenter Custom or Internet Custom, to a connection.
The acceptable values for this parameter are:

- Enabled
- Disabled

```yaml
Type: AutomaticUseCustom
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

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

### -CongestionProvider
Specifies the congestion provider property that TCP uses.
The acceptable values for this parameter are:

- CTCP.
Compound TCP increases the receive window and amount of data sent.
CTCP can improve throughput on higher latency connections.
- DCTCP.
Data Center TCP adjusts the TCP window based on network congestion feedback based on Explicit Congestion Notification (ECN) signaling.
DCTCP may improve throughput on low latency links.
- Default.
Servers use DCTCP by default.
Client computers use NewReno.
For information about NewReno, see [RFC 3782](http://www.ietf.org/rfc/rfc3782.txt).

```yaml
Type: CongestionProvider
Parameter Sets: (All)
Aliases:
Accepted values: Default, CTCP, DCTCP

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CwndRestart
Specifies whether to enable congestion window restart.
Congestion window restart can avoid slow start to optimize throughput on low latency networks.
For more information about congestion window restart, see [RFC 2581](http://www.ietf.org/rfc/rfc2581.txt).
The acceptable values for this parameter are:

- True.
TCP uses congestion window restart.
- False.
TCP uses the default setting of the connection.

```yaml
Type: CwndRestart
Parameter Sets: (All)
Aliases:
Accepted values: False, True

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DelayedAckFrequency
Specifies the number of acknowledgments (ACKs) received before the computer sends a response.

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

### -DelayedAckTimeoutMs
Specifies the time to wait, in milliseconds, before the computer sends an ACK if the computer receives fewer than delayed acknowledgment frequency of packets.
Use the *DelayedAckFrequency* parameter to specify the delayed ACK frequency value.
Reducing the time to wait can increase throughput on low latency networks by accelerating growth in TCP window size.
The acceptable values for this parameter are: increments of 10, from 10 through 600.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: DelayedAckTimeout

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DynamicPortRangeNumberOfPorts
Specifies the number of ports for the dynamic port range that starts from the port that you specify for the *DynamicPortRangeStartPort* parameter.

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

### -DynamicPortRangeStartPort
Specifies the starting port for the dynamic port range.
This parameter sets the starting port to send and receive TCP traffic.
The acceptable values for this parameter are: 1 through 65535.

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

### -EcnCapability
Specifies whether to enable ECN capability.
The acceptable values for this parameter are:

- Enabled.
Uses ECN capability.
- Disabled.
Does not use ECN capability.

If you specify a value of Disabled, UseECT0, or UseEct1 for the *EcnMarking* parameter of the Set-NetIPInterface cmdlet, the current parameter has no effect.

```yaml
Type: EcnCapability
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceWS
Specifies whether to force window scaling for retransmission.
The acceptable values for this parameter are:

- Enabled.
Requires window scaling for retransmission.
- Disabled.
Does not require window scaling for retransmission.

The default value is Disabled.

```yaml
Type: ForceWS
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitialCongestionWindowMss
Specifies the initial size of the congestion window.
Provide a value to multiply by the maximum segment size (MSS).
The acceptable values for this parameter are: even numbers from 2 through 64.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: InitialCongestionWindow

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitialRtoMs
Specifies the period, in milliseconds, before connect, or SYN, retransmit.
The acceptable values for this parameter are: increments of 10, from 300 ms through 3000 ms.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: InitialRto

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

### -MaxSynRetransmissions
Specifies the maximum number of times the computer sends SYN packets without receiving a response.

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

### -MemoryPressureProtection
Specifies whether to use memory pressure protection.
TCP memory pressure protection helps ensure that a computer continues normal operation when low on memory due to denial of service attacks.
The acceptable values for this parameter are:

- Enabled.
When low on memory, during an attack, close existing TCP connections and drop incoming SYN requests.
- Disabled.
Do not use memory pressure protection.
- Default.
Use the computer default value for memory pressure protection.

```yaml
Type: MemoryPressureProtection
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled, Default

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinRtoMs
Specifies a value, in milliseconds, for the TCP retransmission to time out.
The acceptable values for this parameter are: increments of 10, from 20 ms through 300 ms.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: MinRto

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NonSackRttResiliency
Specifies whether to enable round trip time resiliency for clients that do not support selective acknowledgment.
The acceptable values for this parameter are:

- Enabled
- Disabled

```yaml
Type: NonSackRttResiliency
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

### -ScalingHeuristics
Specifies whether to enable scaling heuristics.
The acceptable values for this parameter are:

- Enabled
- Disabled

```yaml
Type: ScalingHeuristics
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SettingName
Specifies an array of setting names.
You can specify only Custom for this parameter.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: False
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

### -Timestamps
Specifies whether to enable timestamps.
Timestamps facilitate round trip measurement, and can help protect against wrapped sequence numbers on high throughput links.
For more information about TCP timestamps, see [RFC 1323](http://www.ietf.org/rfc/rfc1323.txt).
The acceptable values for this parameter are:

- Enabled
- Disabled

```yaml
Type: Timestamps
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetTCPSetting
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-NetTCPSetting](./Get-NetTCPSetting.md)

[Get-NetTransportFilter](./Get-NetTransportFilter.md)

[Get-NetUDPSetting](./Get-NetUDPSetting.md)

[New-NetTransportFilter](./New-NetTransportFilter.md)

[Remove-NetTransportFilter](./Remove-NetTransportFilter.md)

[Set-NetUDPSetting](./Set-NetUDPSetting.md)
