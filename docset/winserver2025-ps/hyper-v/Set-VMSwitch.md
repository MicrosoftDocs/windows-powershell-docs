---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vmswitch?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VMSwitch
---

# Set-VMSwitch

## SYNOPSIS
Configures a virtual switch.

## SYNTAX

### SwitchName_SwitchType (Default)
```
Set-VMSwitch [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-Name] <String[]> [-SwitchType <VMSwitchType>] [-AllowManagementOS <Boolean>]
 [-DefaultFlowMinimumBandwidthAbsolute <Int64>] [-DefaultFlowMinimumBandwidthWeight <Int64>]
 [-DefaultQueueVrssEnabled <Boolean>] [-DefaultQueueVmmqEnabled <Boolean>]
 [-DefaultQueueVmmqQueuePairs <UInt32>] [-Extensions <VMSwitchExtension[]>] [-Notes <String>] [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SwitchObject_SwitchType
```
Set-VMSwitch [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMSwitch] <VMSwitch[]> [-SwitchType <VMSwitchType>] [-AllowManagementOS <Boolean>]
 [-DefaultFlowMinimumBandwidthAbsolute <Int64>] [-DefaultFlowMinimumBandwidthWeight <Int64>]
 [-DefaultQueueVrssEnabled <Boolean>] [-DefaultQueueVmmqEnabled <Boolean>]
 [-DefaultQueueVmmqQueuePairs <UInt32>] [-Extensions <VMSwitchExtension[]>] [-Notes <String>] [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SwitchName_NetAdapterInterfaceDescription
```
Set-VMSwitch [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-Name] <String[]> [-NetAdapterInterfaceDescription] <String> [-AllowManagementOS <Boolean>]
 [-DefaultFlowMinimumBandwidthAbsolute <Int64>] [-DefaultFlowMinimumBandwidthWeight <Int64>]
 [-DefaultQueueVrssEnabled <Boolean>] [-DefaultQueueVmmqEnabled <Boolean>]
 [-DefaultQueueVmmqQueuePairs <UInt32>] [-Extensions <VMSwitchExtension[]>] [-Notes <String>] [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SwitchName_NetAdapterName
```
Set-VMSwitch [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-Name] <String[]> [-NetAdapterName] <String> [-AllowManagementOS <Boolean>]
 [-DefaultFlowMinimumBandwidthAbsolute <Int64>] [-DefaultFlowMinimumBandwidthWeight <Int64>]
 [-DefaultQueueVrssEnabled <Boolean>] [-DefaultQueueVmmqEnabled <Boolean>]
 [-DefaultQueueVmmqQueuePairs <UInt32>] [-Extensions <VMSwitchExtension[]>] [-Notes <String>] [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SwitchObject_NetAdapterInterfaceDescription
```
Set-VMSwitch [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMSwitch] <VMSwitch[]> [-NetAdapterInterfaceDescription] <String> [-AllowManagementOS <Boolean>]
 [-DefaultFlowMinimumBandwidthAbsolute <Int64>] [-DefaultFlowMinimumBandwidthWeight <Int64>]
 [-DefaultQueueVrssEnabled <Boolean>] [-DefaultQueueVmmqEnabled <Boolean>]
 [-DefaultQueueVmmqQueuePairs <UInt32>] [-Extensions <VMSwitchExtension[]>] [-Notes <String>] [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SwitchObject_NetAdapterName
```
Set-VMSwitch [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMSwitch] <VMSwitch[]> [-NetAdapterName] <String> [-AllowManagementOS <Boolean>]
 [-DefaultFlowMinimumBandwidthAbsolute <Int64>] [-DefaultFlowMinimumBandwidthWeight <Int64>]
 [-DefaultQueueVrssEnabled <Boolean>] [-DefaultQueueVmmqEnabled <Boolean>]
 [-DefaultQueueVmmqQueuePairs <UInt32>] [-Extensions <VMSwitchExtension[]>] [-Notes <String>] [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMSwitch** cmdlet configures a virtual switch.

## EXAMPLES

### Example 1
```
PS C:\> Set-VMSwitch WA -SwitchType Internal
```

This example converts a virtual switch named WA to an Internal switch.

### Example 2
```
PS C:\> Set-VMSwitch VMNetwork -NetAdapterName "Ethernet 2"
```

This example attaches a virtual switch named VMNetwork to a physical ethernet adapter named Ethernet 2. This will also implicitly convert the VMNetwork switch to an external switch.

### Example 3
```
PS C:\> Set-VMSwitch CA -DefaultFlowMinimumBandwidthAbsolute 500000000
```

This example sets the minimum bandwidth allocation to 500Mbps on a virtual switch named CA for all virtual machines without explicit minimum bandwidth configuration.

## PARAMETERS

### -AllowManagementOS
Specifies whether the management operating system can use the physical network adapter that is bound to the virtual switch. Setting **AllowManagementOS** to `$true` creates management operating system virtual network adapters (VMNetworkAdapters) in the parent partition and connects it to the virtual switch. Setting **AllowManagementOS** to `$false` removes any VMNetworkAdapters connected to the virtual switch.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: SwitchName_SwitchType, SwitchName_NetAdapterInterfaceDescription, SwitchName_NetAdapterName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: CimSession[]
Parameter Sets: SwitchObject_SwitchType, SwitchObject_NetAdapterInterfaceDescription, SwitchObject_NetAdapterName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual switch is to be configured.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: PSComputerName

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

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultFlowMinimumBandwidthAbsolute
Specifies the minimum bandwidth, in bits per second, that is allocated to a special category called "default flow." Any traffic sent by a virtual network adapter that is connected to this virtual switch and does not have minimum bandwidth allocated is filtered into this category.
Specify a value for this parameter only if the minimum bandwidth mode on this virtual switch is absolute (See the **New-VMSwitch** cmdlet).
By default, the virtual switch allocates 10% of the total bandwidth, which depends on the physical network adapter it binds to, to this category.
For example, if a virtual switch binds to a 1 GbE network adapter, this special category can use at least 100 Mbps.
If the value is not a multiple of 8, the value is rounded down to the nearest number that is a multiple of 8.
For example, a value input as 1234567 is converted to 1234560.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultFlowMinimumBandwidthWeight
Specifies the minimum bandwidth, in relative weight, that is allocated to a special category called "default flow".
Any traffic sent by a virtual network adapter that is connected to this virtual switch and doesn't have minimum bandwidth allocated is filtered into this category.
Specify a value for this parameter only if the minimum bandwidth mode on this virtual switch is weight (See the **New-VMSwitch** cmdlet).
By default, this special category has a weight of 1.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultQueueVmmqEnabled


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

### -DefaultQueueVmmqQueuePairs


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

### -DefaultQueueVrssEnabled


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

### -Extensions
Specifies an ordered list of network extensions used to reorder the bindings on the virtual switch.

```yaml
Type: VMSwitchExtension[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual switch to be configured.

```yaml
Type: String[]
Parameter Sets: SwitchName_SwitchType, SwitchName_NetAdapterInterfaceDescription, SwitchName_NetAdapterName
Aliases: SwitchName

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetAdapterInterfaceDescription
Specifies the interface description of the physical network adapter to which an external virtual switch should be bound.
If you specify this parameter to convert a virtual switch, the external virtual switch is configured to allow the management operating system to share access to the physical network adapter.
To override this behavior, include AllowManagementOs $false in the command

```yaml
Type: String
Parameter Sets: SwitchName_NetAdapterInterfaceDescription, SwitchObject_NetAdapterInterfaceDescription
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetAdapterName
Specifies the name of the physical network adapter to which an external virtual switch should be bound.
If you specify this parameter to convert a virtual switch, the external virtual switch is configured to allow the management operating system to share access to the physical network adapter.
To override this behavior, include AllowManagementOs $false in the command

```yaml
Type: String
Parameter Sets: SwitchName_NetAdapterName, SwitchObject_NetAdapterName
Aliases: InterfaceAlias

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Notes
Specifies notes to be associated with the virtual switch.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.HyperV.PowerShell.EthernetSwitch** object is to be passed through to the pipeline representing the virtual switch to be configured.

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

### -SwitchType
Converts a virtual switch from one type to another.
Allowed values are **Internal** or **Private**.
You can convert an internal or private virtual switch to an external virtual switch, by including either the **NetAdapterInterfaceDescription** or **NetAdapterName** parameter in the command.
If you do this, the external virtual switch is configured to allow the management operating system to share access to the physical network adapter.
To override this behavior, include AllowManagementOs $false in the command.

```yaml
Type: VMSwitchType
Parameter Sets: SwitchName_SwitchType, SwitchObject_SwitchType
Aliases:
Accepted values: Private, Internal, External

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSwitch
Specifies the virtual switch to be configured.

```yaml
Type: VMSwitch[]
Parameter Sets: SwitchObject_SwitchType, SwitchObject_NetAdapterInterfaceDescription, SwitchObject_NetAdapterName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

## OUTPUTS

### None
Default

### Microsoft.HyperV.PowerShell.EthernetSwitch
If **-PassThru** is specified.

## NOTES

## RELATED LINKS

