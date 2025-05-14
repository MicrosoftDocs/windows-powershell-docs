---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vmnetworkadaptervlan?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VMNetworkAdapterVlan
---

# Set-VMNetworkAdapterVlan

## SYNOPSIS
Configures the virtual LAN settings for the traffic through a virtual network adapter.

## SYNTAX

### VMName (Default)
```
Set-VMNetworkAdapterVlan [-VMNetworkAdapterName <String>] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-VMName] <String[]> [-Untagged] [-Access]
 [-VlanId <Int32>] [-Trunk] [-NativeVlanId <Int32>] [-AllowedVlanIdList <String>] [-Isolated] [-Community]
 [-Promiscuous] [-PrimaryVlanId <Int32>] [-SecondaryVlanId <Int32>] [-SecondaryVlanIdList <String>] [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceObject
```
Set-VMNetworkAdapterVlan [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [-Untagged] [-Access] [-VlanId <Int32>]
 [-Trunk] [-NativeVlanId <Int32>] [-AllowedVlanIdList <String>] [-Isolated] [-Community] [-Promiscuous]
 [-PrimaryVlanId <Int32>] [-SecondaryVlanId <Int32>] [-SecondaryVlanIdList <String>] [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ManagementOS
```
Set-VMNetworkAdapterVlan [-ManagementOS] [-VMNetworkAdapterName <String>] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-Untagged] [-Access] [-VlanId <Int32>] [-Trunk]
 [-NativeVlanId <Int32>] [-AllowedVlanIdList <String>] [-Isolated] [-Community] [-Promiscuous]
 [-PrimaryVlanId <Int32>] [-SecondaryVlanId <Int32>] [-SecondaryVlanIdList <String>] [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### VMObject
```
Set-VMNetworkAdapterVlan [-VMNetworkAdapterName <String>] [-VM] <VirtualMachine[]> [-Untagged] [-Access]
 [-VlanId <Int32>] [-Trunk] [-NativeVlanId <Int32>] [-AllowedVlanIdList <String>] [-Isolated] [-Community]
 [-Promiscuous] [-PrimaryVlanId <Int32>] [-SecondaryVlanId <Int32>] [-SecondaryVlanIdList <String>] [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMNetworkAdapterVlan** cmdlet configures virtual LAN settings for the traffic through a virtual network adapter.
Access, Trunk, Private VLAN (isolated, community, or promiscuous), and untagged are mutually exclusive.

## EXAMPLES

### Example 1
```
PS C:\> Set-VMNetworkAdapterVlan -VMName Redmond -Access -VlanId 121
```

Sets the virtual network adapter(s) in virtual machine Redmond to the Access mode.
Traffic sent by this virtual machine is tagged with VLAN ID 121.

### Example 2
```
PS C:\> Set-VMNetworkAdapterVlan -VMName Redmond -Trunk -AllowedVlanIdList 1-100 -NativeVlanId 10
```

Sets the virtual network adapter(s) in virtual machine Redmond to the Trunk mode.
Any traffic tagged with one of the VLAN IDs in the allowed VLAN list will be permitted to be sent or received by the VLAN.
If traffic is untagged, it will be treated as if it were on VLAN 10.

### Example 3
```
PS C:\> Get-VMNetworkAdapter -VMName Redmond | Set-VMNetworkAdapterVlan -Isolated -PrimaryVlanId 10 -SecondaryVlanId 200
```

Gets the virtual network adapters from virtual machine Redmond and sets them to the Private VLAN isolated mode, where primary VLAN is 10 and the secondary VLAN is 200.

### Example 4
```
PS C:\> Get-VMNetworkAdapter -VMName WA | Set-VMNetworkAdapterVlan -Promiscuous -PrimaryVlanId 10 -SecondaryVlanIdList 200-201
```

Gets the virtual network adapters from virtual machine WA and sets them to the Private VLAN promiscuous mode, where primary VLAN is 10 and the secondary VLANs are 201 and 202.

### Example 5
```
PS C:\> Get-VM Redmond | Set-VMNetworkAdapterVlan -Untagged
```

Gets virtual machine Redmond and sets the virtual network adapters in the virtual machine to the untagged mode.

### Example 5
```
PS C:\> Set-VMNetworkAdapterVlan -ManagementOS -Access -VlanID 20
```

Sets the virtual switch in the management OS to the Access mode.
Traffic sent by this virtual switch is tagged with VLAN ID 20.

## PARAMETERS

### -Access
Specifies **Access** mode for the virtual machine network adapter. This parameter configures an untagged virtual port with the VLANId (port based VLAN), so it must be specified together with **VlanId**.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: VMName, ManagementOS
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
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName, ManagementOS
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
Parameter Sets: VMName, ManagementOS
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
parent or host) operating system.

```yaml
Type: SwitchParameter
Parameter Sets: ManagementOS
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
Specifies that a **Microsoft.HyperV.PowerShell.VMNetworkAdapterVlanSetting** object is to be passed through to the pipeline representing the virtual machine network adapter virtual LAN settings to be configured.

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
Specifies **Trunk** mode for the virtual machine network adapter. This parameter configures a tagged virtual port that passes all allowed VLANId tags to the VM adapter. Traffic with the NativeVLANId is passed untagged to the VM adapter.
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
Parameter Sets: VMObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMNetworkAdapter
Specifies the virtual machine network adapter.

```yaml
Type: VMNetworkAdapterBase[]
Parameter Sets: ResourceObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMNetworkAdapterName
Specifies the name of the virtual machine network adapter.

```yaml
Type: String
Parameter Sets: VMName, ManagementOS, VMObject
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

### Microsoft.HyperV.PowerShell.VMNetworkAdapterVlanSetting
If **-PassThru** is specified.

## NOTES

## RELATED LINKS
[Configure and View VLAN Settings on Hyper-V Virtual Switch Ports](/windows-server/virtualization/hyper-v-virtual-switch/configure-and-view-vlan-settings-on-hyper-v-virtual-switch-ports)
