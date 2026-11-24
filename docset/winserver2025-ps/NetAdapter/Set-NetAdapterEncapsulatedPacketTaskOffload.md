---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetAdapterEncapsulatedPacketTaskOffload.cdxml-help.xml
Module Name: NetAdapter
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netadapter/set-netadapterencapsulatedpackettaskoffload?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetAdapterEncapsulatedPacketTaskOffload
---

# Set-NetAdapterEncapsulatedPacketTaskOffload

## SYNOPSIS
Sets the encapsulated packet task offload property of the network adapter.

## SYNTAX

### ByName (Default)
```
Set-NetAdapterEncapsulatedPacketTaskOffload [-Name] <String[]> [-IncludeHidden]
 [-NvgreEncapsulatedPacketTaskOffloadEnabled <Boolean>] [-VxlanEncapsulatedPacketTaskOffloadEnabled <Boolean>]
 [-VxlanUDPPortNumber <UInt16>] [-NoRestart] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInstanceID
```
Set-NetAdapterEncapsulatedPacketTaskOffload -InterfaceDescription <String[]> [-IncludeHidden]
 [-NvgreEncapsulatedPacketTaskOffloadEnabled <Boolean>] [-VxlanEncapsulatedPacketTaskOffloadEnabled <Boolean>]
 [-VxlanUDPPortNumber <UInt16>] [-NoRestart] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetAdapterEncapsulatedPacketTaskOffload -InputObject <CimInstance[]>
 [-NvgreEncapsulatedPacketTaskOffloadEnabled <Boolean>] [-VxlanEncapsulatedPacketTaskOffloadEnabled <Boolean>]
 [-VxlanUDPPortNumber <UInt16>] [-NoRestart] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetAdapterEncapsulatedPacketTaskOffload** cmdlet sets the encapsulated packet task offload property of the network adapter.
Encapsulated task offload allows the network adapter to perform offload operations such as large send offload (LSO) and virtual machine queue (VMQ) on the inner header for encapsulated packets.
The **Enable-NetAdapterEncapsulatedPacketTaskoffload** and **Disable-NetAdapterEncapsulatedPacketTaskOffload** cmdlets can also be used to manage encapsulated packet task offload.

## EXAMPLES

### Example 1: Enable encapsulated packet task offload on the specified network adapter
```
PS C:\> Set-NetAdapterEncapsulatedPacketTaskOffload -Name "MyAdapter" -VxlanEncapsulatedPacketTaskOffloadEnabled $True
```

This command enables VXLAN encapsulated packet task offload on the network adapter named MyAdapter and restarts the network adapter.
The **Enable-NetAdapterEncapsulatedPacketTaskOffload** cmdlet is the preferred cmdlet to perform this operation.

### Example 2: Disable encapsulated packet task offload on the specified network adapter
```
PS C:\> Set-NetAdapterEncapsulatedPacketTaskOffload -Name "MyAdapter" -VxlanEncapsulatedPacketTaskOffloadEnabled $False
```

This command disables VXLAN encapsulated packet task offload on the network adapter named MyAdapter and restarts the network adapter.
The **Disable-NetAdapterEncapsulatedPacketTaskOffload** cmdlet is the preferred cmdlet to perform this operation.

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

### -NvgreEncapsulatedPacketTaskOffloadEnabled
Specifies the enabled state of the Network Virtualization Generic Routing Encapsulation (NVGRE) encapsulated packet task offload in the network adapter. The acceptable values for this parameter are: $true or $false.

```yaml
Type: Boolean
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

### -VxlanEncapsulatedPacketTaskOffloadEnabled
Specifies the enabled state of the Virtual eXtensible Local Area Network (VXLAN) encapsulated packet task offload in the network adapter. The acceptable values for this parameter are: $true or $false.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VxlanUDPPortNumber
Specifies the port number to use for the VXLAN UDP destination port.

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapter EncapsulatedPacketTaskOffloadSettingData[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapter EncapsulatedPacketTaskOffloadSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Disable-NetAdapterEncapsulatedPacketTaskOffload](./Disable-NetAdapterEncapsulatedPacketTaskOffload.md)

[Enable-NetAdapterEncapsulatedPacketTaskOffload](./Enable-NetAdapterEncapsulatedPacketTaskOffload.md)

[Get-NetAdapterEncapsulatedPacketTaskOffload](./Get-NetAdapterEncapsulatedPacketTaskOffload.md)

