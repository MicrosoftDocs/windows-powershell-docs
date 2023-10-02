---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vmnetworkadaptervlan?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-VMNetworkAdapterVlan

## SYNOPSIS
Configures the virtual LAN settings for the traffic through a virtual network adapter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-VMNetworkAdapterVlan [-VMName] <String[]> [-Access] [-AllowedVlanIdList <String>] [-Community]
 [-ComputerName <String[]>] [-Isolated] [-NativeVlanId <Int32>] [-Passthru] [-PrimaryVlanId <Int32>]
 [-Promiscuous] [-SecondaryVlanId <Int32>] [-SecondaryVlanIdList <String>] [-Trunk] [-Untagged]
 [-VlanId <Int32>] [-VMNetworkAdapterName <String>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-VMNetworkAdapterVlan [-Access] [-AllowedVlanIdList <String>] [-Community] [-ComputerName <String[]>]
 [-Isolated] [-NativeVlanId <Int32>] [-Passthru] [-PrimaryVlanId <Int32>] [-Promiscuous]
 [-SecondaryVlanId <Int32>] [-SecondaryVlanIdList <String>] [-Trunk] [-Untagged] [-VlanId <Int32>]
 [-VMNetworkAdapterName <String>] [-ManagementOS] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Set-VMNetworkAdapterVlan [-VM] <VirtualMachine[]> [-Access] [-AllowedVlanIdList <String>] [-Community]
 [-Isolated] [-NativeVlanId <Int32>] [-Passthru] [-PrimaryVlanId <Int32>] [-Promiscuous]
 [-SecondaryVlanId <Int32>] [-SecondaryVlanIdList <String>] [-Trunk] [-Untagged] [-VlanId <Int32>]
 [-VMNetworkAdapterName <String>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Set-VMNetworkAdapterVlan [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [-Access] [-AllowedVlanIdList <String>]
 [-Community] [-Isolated] [-NativeVlanId <Int32>] [-Passthru] [-PrimaryVlanId <Int32>] [-Promiscuous]
 [-SecondaryVlanId <Int32>] [-SecondaryVlanIdList <String>] [-Trunk] [-Untagged] [-VlanId <Int32>] [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Set-VMNetworkAdapterVlan** cmdlet configures virtual LAN settings for the traffic through a virtual network adapter.
Access, Trunk, Private VLAN (isolated, community, or promiscuous), and untagged are mutually exclusive.

## EXAMPLES

### Example 1
```
PS C:\>Set-VMNetworkAdapterVlan -VMName Redmond -Access -VlanId 121
```

Sets the virtual network adapter(s) in virtual machine Redmond to the Access mode.
Traffic sent by this virtual machine  is tagged with VLAN ID 121.

### Example 2
```
PS C:\>Set-VMNetworkAdapterVlan -VMName Redmond -Trunk -AllowedVlanIdList 1-100 -NativeVlanId 10
```

Sets the virtual network adapter(s) in virtual machine Redmond to the Trunk mode.
Any traffic tagged with one of the VLAN IDs in the allowed VLAN list will be permitted to be sent or received by the VLAN.
If traffic is untagged, it will be treated as if it were on VLAN 10.

### Example 3
```
PS C:\>Get-VMNetworkAdapter -VMName Redmond | Set-VMNetworkAdapterVlan -Isolated -PrimaryVlanId 10 -SecondaryVlanId 200
```

Gets the virtual network adapters from virtual machine Redmond and sets them to the Private VLAN isolated mode, where primary VLAN is 10 and the secondary VLAN is 200.

### Example 4
```
PS C:\>Get-VMNetworkAdapter -VMName WA | Set-VMNetworkAdapterVlan -Promiscuous -PrimaryVlanId 10 -SecondaryVlanIdList 200-201
```

Gets the virtual network adapters from virtual machine WA and sets them to the Private VLAN promiscuous mode, where primary VLAN is 10 and the secondary VLANs are 201 and 202.

### Example 5
```
PS C:\>Get-VM Redmond | Set-VMNetworkAdapterVlan -Untagged
```

Gets virtual machine Redmond and sets the virtual network adapters in the virtual machine to the untagged mode.

## PARAMETERS

### -Access
Specifies **Access** mode for the virtual machine network adapter.
This parameter must be specified in conjunction with parameter **VlanId**.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: a

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowedVlanIdList
Specifies a list of virtual LANs allowed on a virtual machine network adapter.
This parameter must be specified in conjunction with the switch parameter **Trunk**.

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

### -Community
Specifies **Community** mode for the virtual machine network adapter to be configured.
This parameter must be specified in conjunction with parameters **PrimaryVlanId** and **SecondaryVlanId**.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: c

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual LAN settings on a virtual machine network adapter are to be configured.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Isolated
Specifies **Isolated** mode for the virtual machine network adapter to be configured.
This parameter must be specified in conjunction with parameters **PrimaryVlanId** and **SecondaryVlanId**.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: i

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementOS
Specifies the management (e.g.
parent OS, or host) operating system.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NativeVlanId
Specifies the native virtual LAN identifier for a virtual machine network adapter.
This parameter must be specified in conjunction with the switch parameter **Trunk**.

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

### -Passthru
Specifies that a **Microsoft.Virtualization.Powershell.VMNetworkAdapterVlanSetting** object is to be passed through to the pipeline representing the virtual machine network adapter virtual LAN settings to be configured.

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

### -PrimaryVlanId
Specifies the primary virtual LAN identifier for a virtual network adapter in **Community**, **Isolated**, or **Promiscuous** mode.

This parameter must be specified in conjunction with parameter **SecondaryVlanId** if the virtual machine network adapter is in **Community** or **Isolated** mode.
It must be used in conjunction with parameter **SecondaryVlanIdList** if the virtual machine network adapter is in **Promiscuous** mode.

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

### -Promiscuous
Specifies **Promiscuous** mode for the virtual machine network adapter.

This parameter must be specified in conjunction with parameters **PrimaryVlanId** and **SecondaryVlanIdList**.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: p

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecondaryVlanId
Specifies the secondary virtual LAN identifier for a virtual network adapter in **Community** or **Isolated** mode.

This parameter must be specified in conjunction with parameter **PrimaryVlanId**, along with switch parameter **Community** or **Isolated**.

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

### -SecondaryVlanIdList
Specifies a list of private virtual LAN secondary virtual LANs on a virtual machine network adapter.This parameter must be specified in conjunction with parameter **PrimaryVlanId** and switch parameter **Promiscuous**.

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

### -Trunk
Specifies **Trunk** mode for the virtual machine network adapter.
This parameter must be used in conjunction with parameters **AllowedVlanIdList** and **NativeVlanId**.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: t

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Untagged
Specifies **Untagged** mode for the virtual machine network adapter.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: u

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine.

```yaml
Type: VirtualMachine[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMNetworkAdapter
Specifies the virtual machine network adapter.

```yaml
Type: VMNetworkAdapterBase[]
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMNetworkAdapterName
Specifies the name of the virtual machine network adapter.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VlanId
Specifies the virtual LAN identifier of a virtual machine network adapter.
This parameter must be specified in conjunction with switch parameter **Access**.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: AccessVlanId

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

## OUTPUTS

### None
Default

### Microsoft.Virtualization.Powershell.VMNetworkAdapterVlanSetting
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



