---
external help file: NetAdapter_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 9E730A08-ADD3-4539-B638-3B18757F88AE
manager: dansimp
---

# Disable-NetAdapterChecksumOffload

## SYNOPSIS
Disables the selected checksum offloads on the network adapter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Disable-NetAdapterChecksumOffload [-Name] <String[]> [-AsJob] [-CimSession <CimSession[]>] [-IncludeHidden]
 [-IpIPv4] [-NoRestart] [-PassThru] [-TcpIPv4] [-TcpIPv6] [-ThrottleLimit <Int32>] [-UdpIPv4] [-UdpIPv6]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Disable-NetAdapterChecksumOffload [-AsJob] [-CimSession <CimSession[]>] [-IpIPv4] [-NoRestart] [-PassThru]
 [-TcpIPv4] [-TcpIPv6] [-ThrottleLimit <Int32>] [-UdpIPv4] [-UdpIPv6] -InputObject <CimInstance[]> [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Disable-NetAdapterChecksumOffload [-AsJob] [-CimSession <CimSession[]>] [-IncludeHidden] [-IpIPv4] [-NoRestart]
 [-PassThru] [-TcpIPv4] [-TcpIPv6] [-ThrottleLimit <Int32>] [-UdpIPv4] [-UdpIPv6]
 -InterfaceDescription <String[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Disable-NetAdapterChecksumOffload** cmdlet disables the selected checksum offloads on the network adapter.
When specified, IPv4, TCPv4, and TCPv6 checksums can be disabled.
If none of these parameters are passed into this cmdlet, then by default all of the checksums for this adapter are disabled.
Physical network adapters have various checksum offloads in which the checksum calculations occur in the network adapter and not in the main processor.
This reduces processor utilization and can increase network throughput.
This cmdlet disables the various checksum offload settings, including IPv4, TCPv4, TCPv6, UDPv4, and UDPv6.
Note: Disabling checksum offload will also disable other stateless offloading including Receive Side Scaling (RSS), Receive Segment Coalescing (RSC) and Large Send Offload (LSO).

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Disable-NetAdapterChecksumOffload -Name * -TcpIPv6
```

This example disables TCP/IPv6 checksum offload on all network adapters and restarts the network adapters.

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

### -IncludeHidden
Specifies both visible and hidden network adapters should be included.
By default only visible network adapters are included.
If a wildcard character is used in identifying a network adapter and this parameter has been specified, then the wildcard string is matched against both hidden and visible network adapters.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
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

### -InterfaceDescription
Specifies the network adapter interface description.
For a physical network adapter this is typically the name of the vendor of the network adapter followed by a part number and description, such as `Contoso 12345 Gigabit Network Device`.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: ifDesc

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -IpIPv4
Specifies that IPv4 checksum offloading is Disabled.

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

### -Name
Specifies the name of the network adapter.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: ifAlias, InterfaceAlias

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -NoRestart
Specifies that the network adapter is not restarted as part of running this cmdlet.
Note: Many advanced properties require restarting the network adapter before the new settings take effect.

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

### -TcpIPv4
Specifies that TCP IPv4 checksum offloading is Disabled.

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

### -TcpIPv6
Specifies that TCP IPv6 checksum offloading is Disabled.

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

### -UdpIPv4
Specifies that UDP IPv4 checksum offloading is Disabled.

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

### -UdpIPv6
Specifies that UDP IPv6 checksum offloading is Disabled.

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapter ChecksumOffloadSettingData[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapter ChecksumOffloadSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Enable-NetAdapterChecksumOffload](./Enable-NetAdapterChecksumOffload.md)

[Get-NetAdapterChecksumOffload](./Get-NetAdapterChecksumOffload.md)

[Set-NetAdapterChecksumOffload](./Set-NetAdapterChecksumOffload.md)

