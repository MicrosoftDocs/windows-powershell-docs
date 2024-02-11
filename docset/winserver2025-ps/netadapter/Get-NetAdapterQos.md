---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetAdapterQos.cdxml-help.xml
Module Name: NetAdapter
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netadapter/get-netadapterqos?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetAdapterQos
---

# Get-NetAdapterQos

## SYNOPSIS
Gets the QoS properties of the network adapter, specifically DCB settings.

## SYNTAX

### ByName (Default)
```
Get-NetAdapterQos [[-Name] <String[]>] [-IncludeHidden] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByInstanceID
```
Get-NetAdapterQos -InterfaceDescription <String[]> [-IncludeHidden] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetAdapterQos** cmdlet gets quality of service (QoS) capabilities and runtime configurations of a DCB-capable network adapter.
If QoS is disabled, then this cmdlet only gets the hardware QoS capabilities of the network adapter.
If QoS is enabled, then this cmdlet gets the operational traffic class and flow control configurations in addition.
If the network adapter supports the DCB Exchange protocol and is connected to a switch that also supports the protocol, then this cmdlet can also return the QoS configurations on the switch.

If a network adapter does not support QoS, specifically DCB, then this cmdlet does not return any information.

## EXAMPLES

### Example 1: Display hardware QoS capabilities and runtime configurations for network adapters where QoS is enabled
```
PS C:\> Get-NetAdapterQos -Name "*" | Where-Object -FilterScript { $_.Enabled }
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

This command displays the hardware QoS capabilities and the runtime QoS configurations for a network adapter on which QoS is enabled.

### Example 2: Display hardware QoS capabilities for network adapters where QoS is disabled
```
PS C:\> Get-NetAdapterQos -Name "*" | Where-Object -FilterScript { $_.Enabled -Eq "False" }
Name         : DCBADAPTER1
Enabled      : False
Capabilities :                       Hardware     Current
--------     -------
MacSecBypass        : NotSupported NotSupported
DcbxSupport         : None         None
NumTCs(Max/ETS/PFC) : 8/8/8        0/0/0
```

This command displays only the hardware QoS capabilities for a network adapter on which QoS is disabled.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
 The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.
 For more information about Windows PowerShell® background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -IncludeHidden
Indicates that the cmdlet includes both visible and hidden network adapters in the operation.
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
Specifies an array of network adapter interface descriptions.
For a physical network adapter this is typically the name of the vendor of the network adapter followed by a part number and description, such as `Contoso 12345 Gigabit Network Device`.

```yaml
Type: String[]
Parameter Sets: ByInstanceID
Aliases: ifDesc, InstanceID

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies an array of network adapter names.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: ifAlias, InterfaceAlias

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterQosSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
The output object contains QoS capabilities and configurations on a network adapter.

## NOTES

## RELATED LINKS

[Disable-NetAdapterQos](./Disable-NetAdapterQos.md)

[Enable-NetAdapterQos](./Enable-NetAdapterQos.md)

[Set-NetAdapterQos](./Set-NetAdapterQos.md)

