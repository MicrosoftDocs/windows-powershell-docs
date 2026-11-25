---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetAdapterQos.cdxml-help.xml
Module Name: NetAdapter
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netadapter/enable-netadapterqos?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-NetAdapterQos
---

# Enable-NetAdapterQos

## SYNOPSIS
Enables QoS on the network adapter, specifically DCB.

## SYNTAX

### ByName (Default)
```
Enable-NetAdapterQos [-Name] <String[]> [-IncludeHidden] [-NoRestart] [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInstanceID
```
Enable-NetAdapterQos -InterfaceDescription <String[]> [-IncludeHidden] [-NoRestart] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Enable-NetAdapterQos -InputObject <CimInstance[]> [-NoRestart] [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-NetAdapterQos** cmdlet enables quality of service (QoS) on a network adapter.
The QoS features, which include traffic class bandwidth allocation and priority based flow control, are specified in the IEEE data center bridging (DCB) standard.
When QoS is enabled and the computer is configured to not accept configurations from a remote device, the computer sends the network adapter the user-generated configurations for the QoS features.
For more information about the configuring the computer not to accept configurations from a remote device, see the **Set-NetQosDcbxSetting** cmdlet.
Otherwise, the network adapter enables the QoS features based on either the factory default configurations or what it receives from the remote device.

To configure traffic class bandwidth allocation and priority based flow control on the computer, you can use the New-NetQosTrafficClass and the **Enable-NetQosFlowControl** cmdlets.

Some switches expect end stations, such as computers running Windows Server® 2012 or later, to accept configurations from the switches.
If the switches detect a mismatched configuration through the data center bridging exchange (DCBX) protocol, then the switches disable the DCB functionalities.
To overcome this limitation, users can disable DCBX on either the switches or the network adapters and manually configure the features on either end.

## EXAMPLES

### Example 1: Enable QoS on the specified network adapter
```
PS C:\> Enable-NetAdapterQos -Name "DCBNIC1"
```

This command enables QoS on a network adapter named DCBNIC1 and restarts the network adapter.

### Example 2: Enable QoS on all network adapters that support QoS
```
This command gets all network adapters that support QoS, enables QoS on all of them, and restarts the network adapter.
PS C:\> $NetAdapter1 = Get-NetAdapterQos -Name "*"
PS C:\> Enable-NetAdapterQos -InputObject $NetAdapter1

This command is a version of the cmdlet that gets all network adapters that support QoS and enables QoS on all of them via the pipeline, then restarts the network adapter.
PS C:\> Get-NetAdapterQos -Name "*" | Enable-NetAdapterQos
```

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

### -IncludeHidden
Indicates that the cmdlet includes both visible and hidden network adapters in the operation.
By default only visible network adapters are included.
If a wildcard character is used in identifying a network adapter and this parameter has been specified, then the wildcard string is matched against both hidden and visible network adapters.

```yaml
Type: SwitchParameter
Parameter Sets: ByName, ByInstanceID
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
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoRestart
Indicates that the cmdlet does not restart the network adapter after completing the operation.
Many advanced properties require restarting the network adapter before the new settings take effect.

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterQosSettingData[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
The input object is a list of network adapter objects, such as output from the **Get-NetAdapter** cmdlet.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterQosSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
The output object contains QoS capabilities and configurations on a network adapter.
The output object is returned only when the *PassThru* parameter is specified.

## NOTES

## RELATED LINKS

[Disable-NetAdapterQos](./Disable-NetAdapterQos.md)

[Get-NetAdapter](./Get-NetAdapter.md)

[Get-NetAdapterQos](./Get-NetAdapterQos.md)

