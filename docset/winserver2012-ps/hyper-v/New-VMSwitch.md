---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/new-vmswitch?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-VMSwitch

## SYNOPSIS
Creates a new virtual switch on one or more virtual machine hosts.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-VMSwitch [-Name] <String> [-AllowManagementOS <Boolean>] [-ComputerName <String[]>] [-EnableIov <Boolean>]
 [-MinimumBandwidthMode <VMSwitchBandwidthMode>] [-Notes <String>] -NetAdapterName <String> [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
New-VMSwitch [-Name] <String> [-AllowManagementOS <Boolean>] [-ComputerName <String[]>] [-EnableIov <Boolean>]
 [-MinimumBandwidthMode <VMSwitchBandwidthMode>] [-Notes <String>] -NetAdapterInterfaceDescription <String>
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
New-VMSwitch [-Name] <String> [-ComputerName <String[]>] [-EnableIov <Boolean>]
 [-MinimumBandwidthMode <VMSwitchBandwidthMode>] [-Notes <String>] -SwitchType <VMSwitchType> [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **New-VMSwitch** cmdlet creates a new virtual switch on one or more virtual machine hosts.

## EXAMPLES

### Example 1
```
PS C:\>New-VMSwitch "QoS Switch" -NetAdapterName "Wired Ethernet Connection 3" -MinimumBandwidthMode Weight
```

Creates a new switch QoS switch, which binds to a network adapter called Wired Ethernet Connection 3 and supports weight-based minimum bandwidth.

## PARAMETERS

### -AllowManagementOS
Specifies whether the parent partition (i.e.
the management operating system) is to have access to the physical NIC bound to the virtual switch to be created.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual switch is to be created.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: PSComputerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableIov
Specifies that IO virtualization is to be enabled on the virtual switch to be created.

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

### -MinimumBandwidthMode
Specifies how minimum bandwidth is to be configured on the virtual switch.
Allowed values are **Absolute**, **Default**, **None**, or **Weight**.
If **Absolute** is specified, minimum bandwidth is bits per second.
If **Weight** is specified, minimum bandwidth is a value ranging from 1 to 100.
If **None** is specified, minimum bandwidth is disabled on the switch - that is, users cannot configure it on any network adapter connected to the switch.
If **Default** is specified, the system will set the mode to **Weight**, if the switch is not IOV-enabled, or **None** if the switch is IOV-enabled.

```yaml
Type: VMSwitchBandwidthMode
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Weight
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the switch to be created.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SwitchName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Notes
Specifies a note to be associated with the switch to be created.

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

### -SwitchType
Specifies the type of the switch to be created.
Allowed values are **Internal** and **Private**.
To create an External virtual switch, specify either the **NetAdapterInterfaceDescription** or the **NetAdapterName** parameter, which implicitly set the type of the virtual switch to External.

```yaml
Type: VMSwitchType
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetAdapterInterfaceDescription
Specifies the interface description of the network adapter to be bound to the switch to be created.
You can use the Get-NetAdapter cmdlet to get the interface description of a network adapter.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: InterfaceDescription

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetAdapterName
Specifies the name of the network adapter to be bound to the switch to be created.
You can use the Get-NetAdapter cmdlet to get the interface description of a network adapter.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: InterfaceAlias

Required: True
Position: Named
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

### Microsoft.Virtualization.Powershell.EthernetSwitch

## NOTES

## RELATED LINKS



