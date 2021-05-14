---
external help file: NetAdapter_Cmdlets.xml
Module Name: NetAdapter
online version: https://docs.microsoft.com/powershell/module/netadapter/get-netadapterqos?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NetAdapterQos

## SYNOPSIS
Gets the quality of service (QoS) properties of the network adapter, specifically data center bridging (DCB) settings.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-NetAdapterQos [[-Name] <String[]>] [-AsJob] [-CimSession <CimSession[]>] [-IncludeHidden]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-NetAdapterQos [-AsJob] [-CimSession <CimSession[]>] [-IncludeHidden] [-ThrottleLimit <Int32>]
 -InterfaceDescription <String[]>
```

## DESCRIPTION
The **Get-NetAdapterQos** cmdlet gets quality of service (QoS) capabilities and runtime configurations of a DCB-capable network adapter.
If QoS is disabled, then this cmdlet only gets the hardware QoS capabilities of the network adapter.
If QoS is enabled, then this cmdlet gets the operational traffic class and flow control configurations in addition.
If the network adapter supports the DCB Exchange protocol and is connected to a switch that also supports the protocol, then this cmdlet can also return the QoS configurations on the switch.

If a network adapter does not support QoS, specifically DCB, then this cmdlet does not return any information.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-NetAdapterQos -Name * | Where-Object -FilterScript { $_.Enabled }
Name                       : DCBADAPTER1 
Enabled                    : True 
Capabilities               :                       Hardware     Current 
--------     ------- 
MacSecBypass        : NotSupported NotSupported 
DcbxSupport         : IEEE         None 
NumTCs(Max/ETS/PFC) : 8/8/8        8/8/8 
 
OperationalTrafficClasses  : TC TSA    Bandwidth Priorities 
-- ---    --------- ---------- 
0  ETS           40 0-3,5-7 
1  ETS           60 4 
 
OperationalFlowControl     : Priority 4 Enabled 
OperationalClassifications : Not Available
```

This example displays the hardware QoS capabilities and the runtime QoS configurations for a network adapter on which QoS is enabled.

### EXAMPLE 2
```
PS C:\> Get-NetAdapterQos -Name * | Where-Object -FilterScript { $_.Enabled -Eq "False" }
Name         : DCBADAPTER1 
Enabled      : False 
Capabilities :                       Hardware     Current 
--------     ------- 
MacSecBypass        : NotSupported NotSupported 
DcbxSupport         : None         None 
NumTCs(Max/ETS/PFC) : 8/8/8        0/0/0
```

This example displays only the hardware QoS capabilities for a network adapter on which QoS is disabled.

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterQosSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The output object contains QoS capabilities and configurations on a network adapter.

## NOTES

## RELATED LINKS

[Where-Object](https://go.microsoft.com/fwlink/p/?LinkID=113423)

[Disable-NetAdapterQos](./Disable-NetAdapterQos.md)

[Enable-NetAdapterQos](./Enable-NetAdapterQos.md)

[Set-NetAdapterQos](./Set-NetAdapterQos.md)

