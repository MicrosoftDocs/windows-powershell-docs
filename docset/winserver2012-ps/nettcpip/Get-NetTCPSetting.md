---
external help file: NetTCPIP_Cmdlets.xml
Module Name: NetTCPIP
online version: https://learn.microsoft.com/powershell/module/nettcpip/get-nettcpsetting?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NetTCPSetting

## SYNOPSIS
Gets information about TCP settings and configuration.

## SYNTAX

```
Get-NetTCPSetting [[-SettingName] <String[]>] [-AsJob] [-AssociatedTransportFilter <CimInstance>]
 [-AutoTuningLevelEffective <AutoTuningLevelEffective[]>]
 [-AutoTuningLevelGroupPolicy <AutoTuningLevelGroupPolicy[]>] [-AutoTuningLevelLocal <AutoTuningLevelLocal[]>]
 [-CimSession <CimSession[]>] [-CongestionProvider <CongestionProvider[]>] [-CwndRestart <CwndRestart[]>]
 [-DelayedAckTimeoutMs <UInt32[]>] [-DynamicPortRangeNumberOfPorts <UInt16[]>]
 [-DynamicPortRangeStartPort <UInt16[]>] [-EcnCapability <EcnCapability[]>]
 [-InitialCongestionWindowMss <UInt32[]>] [-InitialRtoMs <UInt32[]>]
 [-MemoryPressureProtection <MemoryPressureProtection[]>] [-MinRtoMs <UInt32[]>]
 [-ScalingHeuristics <ScalingHeuristics[]>] [-ThrottleLimit <Int32>] [-Timestamps <Timestamps[]>]
```

## DESCRIPTION
The **Get-NetTCPSetting** cmdlet gets information for each TCP setting.
There will be different connection characteristics when connecting over a wide area network and within a data center.
Thus each TCP setting is optimized for different network conditions including latency and congestion.
The default application of the TCP setting is Automatic.
To apply a TCP setting to a specific port number or destination IP address range, use the New-NetTransportFilter cmdlet.

Without parameters, this cmdlet returns all TCP settings.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NetTCPSetting
```

This example gets information about TCP settings and configuration.
Used without parameters gets all TCP settings.

### EXAMPLE 2
```
PS C:\>Get-NetTCPSetting -Setting Internet
```

This example gets information about TCP settings that are optimized for connectivity across the Internet.

### EXAMPLE 3
```
PS C:\>Get-NetTcpSetting | Format-Table
```

This example gets information about TCP settings, and displays a summary in a table view.

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

### -AssociatedTransportFilter
Gets TCP setting information that applies to a specific network transport filter CIM object.
This is typically as input through a pipeline.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AutoTuningLevelEffective
Gets TCP setting information only about a specific AutoTuningLevelEffective property.
TCP auto-tuning improves throughput on high throughput, high latency networks.
AutoTuningLevelEffective determines the effective setting of the TCP auto-tuning level.
The acceptable values for this parameter are:: 

 -- Local: The TCP settings that currently have AutoTuningLevelEffective locally configured. 

 -- GroupPolicy: The TCP settings that currently have AutoTuningLevelEffective configured through group policy.

```yaml
Type: AutoTuningLevelEffective[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutoTuningLevelGroupPolicy
Gets TCP setting information only about a specific AutoTuningLevelGroupPolicy property.
TCP auto-tuning improves throughput on high throughput, high latency networks.
AutoTuningLevelGroupPolicy determines the setting of the TCP auto-tuning level that is configured by group policy.
This group policy is uniformly applied across all NetTcpSettings.
The AutoTuningLevelGroupPolicy settings include (Disabled) set the TCP receive window at its default value; (HighlyRestricted) set TCP to allow the receive window to grow beyond its default value, but do so very conservatively; (Restricted) set TCP to allow the receive window to grow beyond its default value, but does so less conservatively; (Normal) set TCP to allow the receive window to grow to accommodate almost all scenarios; (Experimental) Set TCP to allow the receive window to grow to accommodate extreme scenarios.
(NotConfigured) No group policy is applied for AutoTuningLevel.
The acceptable values for this parameter are:

 -- Disabled: The TCP settings that currently have TCP auto-tuning disabled. 

 -- HighlyRestricted: The TCP settings that have the TCP AutoTuningLevelGroupPolicy as HighlyRestricted. 

 -- Restricted: The TCP settings that currently have TCP AutoTuningLevelGroupPolicy as Restricted. 

 -- Normal: The TCP settings that currently have TCP AutoTuningLevelGroupPolicy as Normal. 

 -- Experimental: The TCP settings that currently have TCP AutoTuningLevelGroupPolicy as Experimental. 

 -- NotConfigured: The TCP settings that currently have TCP AutoTuningLevelGroupPolicy as not configured. 

 -- NotChanged: The TCP settings that currently have TCP AutoTuningLevelGroupPolicy as Not changed.

```yaml
Type: AutoTuningLevelGroupPolicy[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutoTuningLevelLocal
Gets TCP setting information only about a specific AutoTuningLevelLocal property.
TCP auto-tuning improves throughput on high throughput, high latency networks.
AutoTuningLevelLocal determines the setting of the TCP auto-tuning level that is locally configured.
The AutoTuningLevelLocal settings include (Disabled) set the TCP receive window at its default value; (HighlyRestricted) set TCP to allow the receive window to grow beyond its default value, but do so very conservatively; (Restricted) set TCP to allow the receive window to grow beyond its default value, but does so less conservatively; (Normal) set TCP to allow the receive window to grow to accommodate almost all scenarios; (Experimental) Set TCP to allow the receive window to grow to accommodate extreme scenarios.
The acceptable values for this parameter are:

 -- Disabled: The TCP settings that currently have TCP auto-tuning disabled. 

 -- HighlyRestricted: The TCP settings that have the TCP AutoTuningLevelLocal as HighlyRestricted. 

 -- Restricted: The TCP settings that currently have TCP AutoTuningLevelLocal as Restricted. 

 -- Normal: The TCP settings that currently have TCP AutoTuningLevelLocal as Normal. 

 -- Experimental: The TCP settings that currently have TCP AutoTuningLevelLocal as Experimental.

```yaml
Type: AutoTuningLevelLocal[]
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
Gets TCP setting information only for settings that have a specific CongestionProvider.
CongestionProvider determines the congestion provider used by TCP.
The CongestionProvider settings include (Default) the TCP stack uses its default setting.
Servers use DCTCP by default.
Clients use NewReno as defined in RFC 3782http://www.ietf.org/rfc/rfc3782.txt; (CTCP) the TCP stack uses Compound TCP, which increases the receive window and amount of data sent.
This may improve throughput on higher latency connections; (DCTCP) the TCP stack uses Datacenter TCP, which adjusts the TCP window size based on network congestion feedback based on ECN signaling.
This may improve throughput on low latency links.
The acceptable values for this parameter are:

 -- Default: The TCP settings that have the CongestionProvider as Default. 

 -- CTCP: The TCP settings that have the CongestionProvider as Compound TCP. 

 -- DCTCP: The TCP settings that have the CongestionProvider as Data Center TCP.

```yaml
Type: CongestionProvider[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CwndRestart
Gets TCP setting information only for settings that have CwndRestart set to False or True.
CwndRestart determines whether congestion window is restarted and can avoid slow start to optimize throughput on low latency networks.
This is described in RFC 2581http://go.microsoft.com/fwlink/p/?LinkId=95127.
The CwndRestart settings include (False) set the TCP stack uses its default setting; (True) the TCP stack uses CwndRestart.
The acceptable values for this parameter are:

 -- False: The TCP settings that have the CwndRestart as False. 

 -- True: The TCP settings that have the CwndRestart as True.

```yaml
Type: CwndRestart[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DelayedAckTimeoutMs
Gets TCP setting information only for a specific DelayedAckTimeoutMs.
DelayedAckTimeoutMs controls the timeout, in milliseconds, for sending an ACK when less than delackfrequency packets are received.
Reducing this time will potentially benefit throughput on low latency networks by accelerating growth in TCP window size.
The acceptable values for this parameter are: 10 through 600.

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

### -DynamicPortRangeNumberOfPorts
Gets TCP setting information only for a specific DynamicPortRangeNumberOfPorts.
DynamicPortRangeNumberOfPorts specifies the number of ports for the dynamic port range starting from the DynamicPortRangeStartPort.

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

### -DynamicPortRangeStartPort
Gets TCP setting information only for a specific DynamicPortRangeStartPort.
DynamicPortRangeStartPort specifies the starting port to send TCP traffic.
The acceptable values for this parameter are: 1 through 65535.

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

### -EcnCapability
Gets TCP setting information only for settings if they have EcnCapability enabled or disabled.
EcnCapability controls if a TCP setting can use the ECN Capability on the system.
If the NetIPInterface setting of ECNMarking is disabled or has a static setting configured to UseECT0 or UseEct1, then this setting will not have an effect.
The acceptable values for this parameter are:

 -- Enabled: The TCP settings that have the EcnCapability as Enabled. 

 -- Disabled: The TCP settings that have the EcnCapability as Disabled.

```yaml
Type: EcnCapability[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitialCongestionWindowMss
Gets TCP setting information only for a specific InitialCongestionWindowMss.
InitialCongestionWindowMss determines the initial congestion window in Maximum Segment Size.
The acceptable values for this parameter are: 2 through 64.

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

### -InitialRtoMs
Gets TCP setting information only for a specific InitialRtoMs.
InitialRtoMs determines the connect (SYN) retransmit timeout, in milliseconds.
The default value is `3000`.

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

### -MemoryPressureProtection
Gets the MemoryPressureProtection property.
TCP memory pressure protection ensures the computer can continue normal operation when in low on memory due to DoS attacks.
When enabled, in low memory, and a DoS attack is in progress, MemoryPressureProtection will kill the existing TCP connections and drop incoming SYN requests.
Enabled by default on servers and Disabled by default on clients.
The acceptable values for this parameter are:

 -- Disabled: The TCP settings that have TCP memory pressure protection Disabled. 

 -- Enabled: The TCP settings that have TCP memory pressure protection Enabled. 

 -- Default: The TCP settings that have TCP memory pressure protection set to Default.

```yaml
Type: MemoryPressureProtection[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinRtoMs
Gets TCP setting information only for a specific MinRtoMs.
MinRtoMs determines the TCP retransmission timeout, in milliseconds.
The acceptable values for this parameter are: 20 through 300.

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

### -ScalingHeuristics
Gets TCP setting information only for a specific ScalingHeuristics setting.
The acceptable values for this parameter are:

 -- Disabled: The TCP settings that have ScalingHeuristics disabled. 

 -- Enabled: The TCP settings that have ScalingHeuristics enabled.

```yaml
Type: ScalingHeuristics[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SettingName
Gets TCP setting information for a specific SettingName.
Each SettingName determines the TCP settings applied to each TCP connection.
The acceptable values for this parameter are:

 -- Internet: The TCP settings that are optimized for networks with higher latency and lower throughput. 

 -- Datacenter: The TCP settings that are optimized for networks with lower latency and higher throughput. 

 -- Compat: The TCP settings that are optimized for compatibility with legacy network equipment. 

 -- Custom: The TCP settings that are defined by the administrator. 

 -- Automatic: The computer uses latency, measured by TCP round trip time (RTT), to dynamically apply Internet or Datacenter settings.
For low latency links, 10 milliseconds or less, the computer will apply Datacenter settings.
For higher latency links, greater than 10 milliseconds, the computer will apply Internet settings.

```yaml
Type: String[]
Parameter Sets: (All)
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
Controls RFC 1323http://go.microsoft.com/fwlink/p/?LinkId=84406 TCP timestamps.
RFC 1323http://go.microsoft.com/fwlink/p/?LinkId=84406 timestamps can help with round trip measurement and protection against wrapped sequence numbers on high throughput links.
The default value is Disabled.
The acceptable values for this parameter are:

 -- Disabled: The TCP settings that have RFC 1323http://go.microsoft.com/fwlink/p/?LinkId=84406 timestamps disabled. 

 -- Enabled: The TCP settings that have the RFC 1323http://go.microsoft.com/fwlink/p/?LinkId=84406 timestamps enabled.

```yaml
Type: Timestamps[]
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetTCPSetting
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Format-Table](https://go.microsoft.com/fwlink/p/?LinkId=113302)

[New-NetTransportFilter](./New-NetTransportFilter.md)

[Set-NetTCPSetting](./Set-NetTCPSetting.md)

