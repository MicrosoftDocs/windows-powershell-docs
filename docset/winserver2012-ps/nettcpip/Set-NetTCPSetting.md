---
external help file: NetTCPIP_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 686DF988-37EE-46A5-9D83-96AE147D53B7
manager: dansimp
---

# Set-NetTCPSetting

## SYNOPSIS
Modifies TCP settings and configuration.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NetTCPSetting [[-SettingName] <String[]>] [-AsJob] [-AutoTuningLevelLocal <AutoTuningLevelLocal>]
 [-CimSession <CimSession[]>] [-CongestionProvider <CongestionProvider>] [-CwndRestart <CwndRestart>]
 [-DelayedAckTimeoutMs <UInt32>] [-DynamicPortRangeNumberOfPorts <UInt16>]
 [-DynamicPortRangeStartPort <UInt16>] [-EcnCapability <EcnCapability>] [-InitialCongestionWindowMss <UInt32>]
 [-InitialRtoMs <UInt32>] [-MemoryPressureProtection <MemoryPressureProtection>] [-MinRtoMs <UInt32>]
 [-PassThru] [-ScalingHeuristics <ScalingHeuristics>] [-ThrottleLimit <Int32>] [-Timestamps <Timestamps>]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-NetTCPSetting [-AsJob] [-AutoTuningLevelLocal <AutoTuningLevelLocal>] [-CimSession <CimSession[]>]
 [-CongestionProvider <CongestionProvider>] [-CwndRestart <CwndRestart>] [-DelayedAckTimeoutMs <UInt32>]
 [-DynamicPortRangeNumberOfPorts <UInt16>] [-DynamicPortRangeStartPort <UInt16>]
 [-EcnCapability <EcnCapability>] [-InitialCongestionWindowMss <UInt32>] [-InitialRtoMs <UInt32>]
 [-MemoryPressureProtection <MemoryPressureProtection>] [-MinRtoMs <UInt32>] [-PassThru]
 [-ScalingHeuristics <ScalingHeuristics>] [-ThrottleLimit <Int32>] [-Timestamps <Timestamps>]
 -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-NetTCPSetting** cmdlet modifies information for each TCP setting.
There will be different connection characteristics when connecting over a wide area network and within a data center.
Thus each TCP setting is optimized for different network conditions including latency and congestion.
The only modifiable TCP SettingName is Custom.
To apply a TCP setting to a specific port number or destination IP address range, use the New-NetTransportFilter cmdlet.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-NetTCPSetting -SettingName Custom -InitialCongestionWindow 6 -CongestionProvider CTCP
```

This example sets the custom TCP setting to have a larger initial congestion window and use compound TCP.

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

### -AutoTuningLevelLocal
Modifies the AutoTuningLevelLocal property.
TCP auto-tuning improves throughput on high throughput, high latency networks.
This parameter value determines the setting of the TCP auto-tuning level that is locally configured.
The acceptable values for this parameter are:

 -- Disabled: Sets the TCP receive window at the default value. 

 -- HighlyRestricted: Sets TCP to allow the receive window to grow beyond the default value, but does so very conservatively. 

 -- Restricted: Sets TCP to allow the receive window to grow beyond the default value, but does so less conservatively. 

 -- Normal: Sets TCP to allow the receive window to grow to accommodate almost all scenarios. 

 -- Experimental: Sets TCP to allow the receive window to grow to accommodate extreme scenarios.

```yaml
Type: AutoTuningLevelLocal
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

### -CongestionProvider
Modifies the CongestionProvider property used by TCP.
The acceptable values for this parameter are:

 -- Default: Sets the TCP stack to its default setting.
Servers use DCTCP by default.
Clients use NewReno as defined in RFC 3782http://www.ietf.org/rfc/rfc3782.txt. 

 -- CTCP: Sets the TCP stack to use Compound TCP, which increases the receive window and amount of data sent.
This may improve throughput on higher latency connections. 

 -- DCTCP: Sets the TCP stack to use Datacenter TCP, which adjusts the TCP window size based on network congestion feedback based on ECN signaling.
This may improve throughput on low latency links.

```yaml
Type: CongestionProvider
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CwndRestart
Specifies the enabled state of the cwnd restart.
This parameter value determines whether congestion window is restarted and can avoid slow start to optimize throughput on low latency networks.
This is described in RFC 2581http://go.microsoft.com/fwlink/p/?LinkId=95127. 

 -- False: Sets the TCP stack to use its default setting. 

 -- True: Sets the TCP stack to use cwnd restart.

```yaml
Type: CwndRestart
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DelayedAckTimeoutMs
Modifies the DelayedAckTimeoutMs property.
This parameter value controls the timeout, in milliseconds, for sending an ACK when less than delackfrequency packets are received.
Reducing this time will potentially benefit throughput on low latency networks by accelerating growth in TCP window size. 
The acceptable values for this parameter are: 10 through 600 milliseconds.
This parameter must be specified in increments of 10 milliseconds.

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

### -DynamicPortRangeNumberOfPorts
Modifies the DynamicPortRangeNumberOfPorts property.
This parameter value specifies the number of ports for the dynamic port range starting from the **DynamicPortRangeStartPort** parameter.

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
Modifies the DynamicPortRangeStartPort property.
This parameter value specifies the starting port to send TCP traffic.
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
Specifies the enabled state of the ECN capability.
If the NetIPInterface setting of ECNMarking is disabled or has a static setting configured to UseECT0 or UseEct1, then this setting will not have an effect.
The acceptable values for this parameter are:

 -- Enabled: The TCP setting can use the ECN Capability. 

 -- Disabled: The TCP setting cannot use the ECN Capability.

```yaml
Type: EcnCapability
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitialCongestionWindowMss
Modifies the InitialCongestionWindowMss property.
This parameter value determines the initial congestion window in Maximum Segment Size (MSS).
The acceptable values for this parameter are: 2 through 64 MSS.
This parameter value must be an even number.

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

### -InitialRtoMs
Modifies the InitialRtoMs property.
This parameter value determines the connect (SYN) retransmit timeout, in milliseconds. 
The acceptable values for this parameter are: 300 through 3000 milliseconds.
This parameter must be specified in increments of 10 milliseconds. 

The default value is 3000.

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MemoryPressureProtection
Modifies the MemoryPressureProtection property.
TCP memory pressure protection ensures the computer can continue normal operation when in low on memory due to DoS attacks.
When enabled, in low memory, and a DoS attack is in progress, this parameter value will kill the existing TCP connections and drop incoming SYN requests.
Enabled by default on servers and Disabled by default on clients.
The acceptable values for this parameter are:

 -- Disabled: Turns off TCP memory pressure protection. 

 -- Enabled: Turns on TCP memory pressure protection. 

 -- Default: Restores the TCP memory pressure protection property to computer defaults.

```yaml
Type: MemoryPressureProtection
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinRtoMs
Modifies the MinRtoMs property.
This parameter value determines the TCP retransmission timeout, in milliseconds. 
The acceptable values for this parameter are: 20 through 300 milliseconds.
This parameter must be specified in increments of 10 milliseconds.

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

### -ScalingHeuristics
Specifies the enabled state of the scaling heuristics setting.
The acceptable values for this parameter are:

 -- Disabled: The TCP setting cannot use scaling heuristics. 

 -- Enabled: The TCP setting uses scaling heuristics.

```yaml
Type: ScalingHeuristics
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SettingName
Specifies TCP setting information for a specific setting name.
The only setting name that may be defined by an administrator is Custom.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
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
Specifies the enabled state of the RFC 1323http://www.ietf.org/rfc/rfc1323.txt TCP timestamps.
RFC 1323http://go.microsoft.com/fwlink/p/?LinkId=84406 timestamps can help with round trip measurement and protection against wrapped sequence numbers on high throughput links.
The acceptable values for this parameter are:

 -- Disabled: The TCP setting does not use the RFC 1323http://go.microsoft.com/fwlink/p/?LinkId=84406 timestamps.
This is the default. 

 -- Enabled: The TCP setting uses the RFC 1323http://go.microsoft.com/fwlink/p/?LinkId=84406 timestamps.

```yaml
Type: Timestamps
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

