---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/set-vmswitch?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-VMSwitch

## SYNOPSIS
Configures a virtual switch.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-VMSwitch [-Name] <String[]> [-AllowManagementOS <Boolean>] [-ComputerName <String[]>]
 [-DefaultFlowMinimumBandwidthAbsolute <Int64>] [-DefaultFlowMinimumBandwidthWeight <Int64>]
 [-Extensions <VMSwitchExtension[]>] [-Notes <String>] [-Passthru] [-SwitchType <VMSwitchType>] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-VMSwitch [-Name] <String[]> [-NetAdapterInterfaceDescription] <String> [-AllowManagementOS <Boolean>]
 [-ComputerName <String[]>] [-DefaultFlowMinimumBandwidthAbsolute <Int64>]
 [-DefaultFlowMinimumBandwidthWeight <Int64>] [-Extensions <VMSwitchExtension[]>] [-Notes <String>] [-Passthru]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Set-VMSwitch [-VMSwitch] <VMSwitch[]> [-NetAdapterInterfaceDescription] <String> [-AllowManagementOS <Boolean>]
 [-ComputerName <String[]>] [-DefaultFlowMinimumBandwidthAbsolute <Int64>]
 [-DefaultFlowMinimumBandwidthWeight <Int64>] [-Extensions <VMSwitchExtension[]>] [-Notes <String>] [-Passthru]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Set-VMSwitch [-VMSwitch] <VMSwitch[]> [-AllowManagementOS <Boolean>] [-ComputerName <String[]>]
 [-DefaultFlowMinimumBandwidthAbsolute <Int64>] [-DefaultFlowMinimumBandwidthWeight <Int64>]
 [-Extensions <VMSwitchExtension[]>] [-Notes <String>] [-Passthru] [-SwitchType <VMSwitchType>] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Set-VMSwitch [-Name] <String[]> [-NetAdapterName] <String> [-AllowManagementOS <Boolean>]
 [-ComputerName <String[]>] [-DefaultFlowMinimumBandwidthAbsolute <Int64>]
 [-DefaultFlowMinimumBandwidthWeight <Int64>] [-Extensions <VMSwitchExtension[]>] [-Notes <String>] [-Passthru]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_6
```
Set-VMSwitch [-VMSwitch] <VMSwitch[]> [-NetAdapterName] <String> [-AllowManagementOS <Boolean>]
 [-ComputerName <String[]>] [-DefaultFlowMinimumBandwidthAbsolute <Int64>]
 [-DefaultFlowMinimumBandwidthWeight <Int64>] [-Extensions <VMSwitchExtension[]>] [-Notes <String>] [-Passthru]
 [-Confirm] [-WhatIf]
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
PS C:\> Set-VMSwitch CA -DefaultFlowMinimumBandwidthAbsolute 500000000
```

This example sets the minimum bandwidth allocation to 500Mbps on a virtual switch named CA for all virtual machines without explicit minimum bandwidth configuration.

## PARAMETERS

### -AllowManagementOS
Specifies whether the management operating system can use the physical network adapter that is bound to the external virtual switch.

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

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual switch is to be configured.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: PSComputerName

Required: False
Position: Named
Default value: .
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultFlowMinimumBandwidthAbsolute
Specifies the minimum bandwidth, in bits per second, that is allocated to a special category called "default flow." Any traffic sent by a virtual network adapter that is connected to this virtual switch and does not have minimum bandwidth allocated is filtered into this category.
Specify a value for this parameter only if the minimum bandwidth mode on this virtual switch is absolute (See the New-VMSwitch cmdlet).
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
Specify a value for this parameter only if the minimum bandwidth mode on this virtual switch is weight (See the New-VMSwitch cmdlet).
By default, this special category has a weight of 1.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 10
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_5
Aliases: SwitchName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
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
Specifies that a **Microsoft.Virtualization.Powershell.EthernetSwitch** object is to be passed through to the pipeline representing the virtual switch to be configured.

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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
Aliases: 

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
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_6
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NetAdapterInterfaceDescription
Specifies the interface description of the physical network adapter to which an external virtual switch should be bound.
If you specify this parameter to convert a virtual switch, the external virtual switch is configured to allow the management operating system to share access to the physical network adapter.
To override this behavior, include AllowManagementOs $false in the command

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 2
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
Parameter Sets: UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_6
Aliases: InterfaceAlias

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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

## OUTPUTS

### None
Default

### Microsoft.Virtualization.Powershell.EthernetSwitch
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



