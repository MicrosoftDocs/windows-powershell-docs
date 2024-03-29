---
external help file: NetAdapter_Cmdlets.xml
Module Name: NetAdapter
online version: https://learn.microsoft.com/powershell/module/netadapter/enable-netadapterlso?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Enable-NetAdapterLso

## SYNOPSIS
Enables the large send offload (LSO) properties, such as LSOv4 and LSOv6, of the network adapter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Enable-NetAdapterLso [-Name] <String[]> [-AsJob] [-CimSession <CimSession[]>] [-IncludeHidden] [-IPv4] [-IPv6]
 [-NoRestart] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Enable-NetAdapterLso [-AsJob] [-CimSession <CimSession[]>] [-IPv4] [-IPv6] [-NoRestart] [-PassThru]
 [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Enable-NetAdapterLso [-AsJob] [-CimSession <CimSession[]>] [-IncludeHidden] [-IPv4] [-IPv6] [-NoRestart]
 [-PassThru] [-ThrottleLimit <Int32>] -InterfaceDescription <String[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Enable-NetAdapterLso** cmdlet enables the state of the large send offload (LSO) settings, such as LSOv4 and LSOv6, on the network adapter.
If neither LSOv4 or LSOv6 is specified, then both LSOv4 and LSOv6 are enabled.
LSO is a technology in which the work of segmenting data into network frames is performed by the network adapter instead of by the TCP/IP stack.
With LSO, TCP/IP sends very large data packets down to the network adapter driver and the network adapter hardware.
The network adapter separates the data into smaller network-sized frames.
This increases the speed of high-end send operations and decreases the processor usage of the computer, because the work is performed on the network adapter.
To enable just LSOv4 or LSOv6, run the Set-NetAdapterLso cmdlet.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Enable-NetAdapterLso -Name *
```

This example enables LSO for both IPv4 and IPv6 on all visible network adapters and restarts the network adapters.

### EXAMPLE 2
```
PS C:\>Enable-NetAdapterLso -Name * -IPv4 -IPv6
```

This example enables LSO for both IPv4 and IPv6 on all visible network adapters by explicitly specifying the parameters and then restarts the network adapters.

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

### -IPv4
Specifies that this cmdlet affects IPv4 traffic.

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

### -IPv6
Specifies that this cmdlet affects IPv6 traffic.

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterLsoSettingData[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterLsoSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Disable-NetAdapterLso](./Disable-NetAdapterLso.md)

[Get-NetAdapterLso](./Get-NetAdapterLso.md)

[Set-NetAdapterLso](./Set-NetAdapterLso.md)

