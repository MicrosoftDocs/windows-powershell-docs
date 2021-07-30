---
external help file: NetAdapter_Cmdlets.xml
Module Name: NetAdapter
online version: https://docs.microsoft.com/powershell/module/netadapter/enable-netadapterqos?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Enable-NetAdapterQos

## SYNOPSIS
Enables quality of service (QoS) on the network adapter, specifically data center bridging (DCB).

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Enable-NetAdapterQos [-Name] <String[]> [-AsJob] [-CimSession <CimSession[]>] [-IncludeHidden] [-NoRestart]
 [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Enable-NetAdapterQos [-AsJob] [-CimSession <CimSession[]>] [-NoRestart] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Enable-NetAdapterQos [-AsJob] [-CimSession <CimSession[]>] [-IncludeHidden] [-NoRestart] [-PassThru]
 [-ThrottleLimit <Int32>] -InterfaceDescription <String[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Enable-NetAdapterQos** cmdlet enables quality of service (QoS) on a network adapter.
The QoS features, which include traffic class bandwidth allocation and priority based flow control, are specified in the IEEE data center bridging (DCB) standard.
When QoS is enabled and the computer is configured not to accept configurations from a remote device, the computer will send to the network adapter the user-generated configurations for the QoS features.
For more information about the configuring the computer not to accept configurations from a remote device, see the Set-NetQosDcbxSetting cmdlet.
Otherwise, the network adapter will enable the QoS features based on either the factory default configurations or what it receives from the remote device.

To configure traffic class bandwidth allocation and priority based flow control on the computer, users can run the New-NetQosTrafficClass and the Enable-NetQosFlowControl cmdlets.

Some switches expect end stations, such as computers running Windows Server® 2012 or later, to accept configurations from the switches.
If the switches detect a mismatched configuration via the data center bridging exchange (DCBX) protocol, then the switches disable the DCB functionalities.
To overcome this limitation, users can disable DCBX on either the switches or the network adapters and manually configure the features on either end.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Enable-NetAdapterQos -Name "DCBNIC1"
```

This example enables QoS on a network adapter named DCBNIC1 and restarts the network adapter.

### EXAMPLE 2
```
PS C:\>$netadapter1 = Get-NetAdapterQos -Name *



PS C:\>Enable-NetAdapterQos -InputObject $netadapter1


This is a version of the cmdlet that gets all network adapters that support QoS and enables QoS on all of them via the pipeline, then restarts the network adapter.
PS C:\>Get-NetAdapterQos -Name * | Enable-NetAdapterQos
```

This example gets all network adapters that support QoS, enables QoS on all of them, and restarts the network adapter.

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

### -Name
Specifies the name of the network adapter.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: ifAlias, InterfaceA;ias

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterQosSettingData[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The input object is a list of network adapter objects, such as output from the Get-NetAdapter cmdlet.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterQosSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The output object contains QoS capabilities and configurations on a network adapter.
The output object is returned only when the **PassThru** parameter is specified.

## NOTES

## RELATED LINKS

[Disable-NetAdapterQos](./Disable-NetAdapterQos.md)

[Get-NetAdapter](./Get-NetAdapter.md)

[Get-NetAdapterQos](./Get-NetAdapterQos.md)

[Enable-NetQosFlowControl](../dcbqos/Enable-NetQosFlowControl.md)

[New-NetQosTrafficClass](../dcbqos/New-NetQosTrafficClass.md)

[Set-NetQosDcbxSetting](../dcbqos/Set-NetQosDcbxSetting.md)

