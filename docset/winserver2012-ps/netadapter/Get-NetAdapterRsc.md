---
external help file: NetAdapter_Cmdlets.xml
Module Name: NetAdapter
online version: https://docs.microsoft.com/powershell/module/netadapter/get-netadapterrsc?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NetAdapterRsc

## SYNOPSIS
Gets network adapters that support receive segment coalescing (RSC).

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-NetAdapterRsc [[-Name] <String[]>] [-AsJob] [-CimSession <CimSession[]>] [-IncludeHidden]
 [-IPv4FailureReason <FailureReason[]>] [-IPv4OperationalState <Boolean[]>]
 [-IPv6FailureReason <FailureReason[]>] [-IPv6OperationalState <Boolean[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-NetAdapterRsc [-AsJob] [-CimSession <CimSession[]>] [-IncludeHidden] [-IPv4FailureReason <FailureReason[]>]
 [-IPv4OperationalState <Boolean[]>] [-IPv6FailureReason <FailureReason[]>] [-IPv6OperationalState <Boolean[]>]
 [-ThrottleLimit <Int32>] -InterfaceDescription <String[]>
```

## DESCRIPTION
The **Get-NetAdapterRsc** cmdelt gets network adapters that support receive segment coalescing (RSC).
RSC takes multiple packets received within the same interrupt period and combines the packets into a single large package to be processed by the network stack.
This reduces the processing overhead for incoming packets and reduces the number of processor cycles that are used, leading to better scalability.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NetAdapterRsc -Name MyAdapter
```

This example gets the RSC properties of the network adapter named MyAdapter.

### EXAMPLE 2
```
PS C:\>Get-NetAdapterRsc -Name *
```

This example gets all of the RSC capable network adapters.

### EXAMPLE 3
```
PS C:\>Get-NetAdapterRsc -Name * | Where-Object -FilterScript { $_.Enabled }
```

This example gets all of the RSC capable network adapters.

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterfaceDescription
Specifies the network adapter interface description.
For a physical network adapter this is typically the name of the vendor of the network adapter followed by a part number and description, such as `Contoso 12345 Gigabit Network Device`.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: ifDesc

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -IPv4FailureReason
Returns the reason that RSC may not be working on IPv4 traffic.
The acceptable values for this parameter are: NoFailure, NicPropertyDisabled, WFPCompatibility, NDISCompatibility, ForwardingEnabled, or NetOffloadGlobalDisabled.
If RSC is desired, then the following actions can be taken: 

 - NicPropertyDisabled: Run the Enable-NetAdapterRsc cmdlet to enable RSC on the specified network adapter. 

 - WFPCompatibility: Disable the WFP filters. 

 - NDISCompatibility: Upgrade to an NDIS 6.30 driver. 

 - ForwardingEnabled: Disable forwarding. 

 - NetOffloadGlobalDisabled: Run the Set-NetOffloadGlobalSetting cmdlet with the **ReceiveSegmentCoalescing** parameter set to Enabled.

```yaml
Type: FailureReason[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv4OperationalState
Specifies the state of the TCP/IP protocol driver for RSC.
See the **IPv4FailureReason** parameter value for more information.

```yaml
Type: Boolean[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv6FailureReason
Returns the reason that of RSC may not be working on IPv6 traffic.
The acceptable values for this parameter are: NoFailure, NicPropertyDisabled, WFPCompatibility, NDISCompatibility,  ForwardingEnabled, or NetOffloadGlobalDisabled.
If RSC is desired, then the following actions can be taken: 

For NicPropertyDisabled: Run the Enable-NetAdapterRsc cmdlet to enable RSC on the specified network adapter. 

 - WFPCompatibility: Disable the WFP filters. 

 - NDISCompatibility: Upgrade to an NDIS 6.30 driver. 

 - ForwardingEnabled: Disable forwarding. 

 - NetOffloadGlobalDisabled: Run the Set-NetOffloadGlobalSetting cmdlet with the **ReceiveSegmentCoalescing** parameter set to Enabled.

```yaml
Type: FailureReason[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv6OperationalState
Specifies the state of the TCP/IP protocol driver for RSC.
See the **IPv6FailureReason** parameter value for more information.

```yaml
Type: Boolean[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the network adapter.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: ifAlias, InterfaceAlias

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterRscSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Where-Object](https://go.microsoft.com/fwlink/p/?LinkId=113423)

[Disable-NetAdapterRsc](./Disable-NetAdapterRsc.md)

[Enable-NetAdapterRsc](./Enable-NetAdapterRsc.md)

[Set-NetAdapterRsc](./Set-NetAdapterRsc.md)

[Set-NetOffloadGlobalSetting](../nettcpip/Set-NetOffloadGlobalSetting.md)

