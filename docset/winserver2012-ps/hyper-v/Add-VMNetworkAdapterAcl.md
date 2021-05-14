---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/add-vmnetworkadapteracl?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-VMNetworkAdapterAcl

## SYNOPSIS
Creates an ACL to apply to the traffic through a virtual machine network adapter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-VMNetworkAdapterAcl [-VMName] <String[]> [-ComputerName <String[]>] [-LocalIPAddress <String[]>]
 [-LocalMacAddress <String[]>] [-Passthru] [-RemoteIPAddress <String[]>] [-RemoteMacAddress <String[]>]
 [-VMNetworkAdapterName <String>] -Action <VMNetworkAdapterAclAction> -Direction <VMNetworkAdapterAclDirection>
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Add-VMNetworkAdapterAcl [-ComputerName <String[]>] [-LocalIPAddress <String[]>] [-LocalMacAddress <String[]>]
 [-Passthru] [-RemoteIPAddress <String[]>] [-RemoteMacAddress <String[]>] [-VMNetworkAdapterName <String>]
 -Action <VMNetworkAdapterAclAction> -Direction <VMNetworkAdapterAclDirection> [-ManagementOS] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Add-VMNetworkAdapterAcl [-VM] <VirtualMachine[]> [-LocalIPAddress <String[]>] [-LocalMacAddress <String[]>]
 [-Passthru] [-RemoteIPAddress <String[]>] [-RemoteMacAddress <String[]>] [-VMNetworkAdapterName <String>]
 -Action <VMNetworkAdapterAclAction> -Direction <VMNetworkAdapterAclDirection> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Add-VMNetworkAdapterAcl [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [-LocalIPAddress <String[]>]
 [-LocalMacAddress <String[]>] [-Passthru] [-RemoteIPAddress <String[]>] [-RemoteMacAddress <String[]>]
 -Action <VMNetworkAdapterAclAction> -Direction <VMNetworkAdapterAclDirection> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-VMNetworkAdapterAcl** cmdlet creates an ACL to apply to the traffic through a virtual machine network adapter.
When a virtual network adapter is created there is no ACL on it.
Given a list of IP-based ACL entries to be applied to traffic in the same direction, the longest match rule decides which one of the entries is most appropriate to apply to a specific packet.

## EXAMPLES

### Example 1
```
PS C:\>Add-VMNetworkAdapterAcl -VMName Redmond -RemoteIPAddress 10.0.0.0/8 -Direction Both -Action Allow
```

This example adds an ACL to allow virtual machine Redmond to send to and receive from traffic on IP subnet 10.0.0.8/8.

### Example 2
```
PS C:\>Add-VMNetworkAdapterAcl -VMName Redmond -RemoteIPAddress ANY -Direction Both -Action Deny
```

This example adds an ACL to deny virtual machine Redmond to send either IPv4 or IPv6 traffic to anywhere and receive such traffic from anywhere.

### Example 3
```
PS C:\>Get-VM Redmond | Add-VMNetworkAdapterAcl -RemoteMacAddress 03-0f-01-0e-aa-b2 -Direction Both -Action Deny
```

This example gets virtual machine Redmond and adds an ACL to deny it to send any traffic to a device with MAC address 03-0f-01-0e-aa-b2 or to receive any traffic from that device.

### Example 4
```
PS C:\>Get-VMNetworkAdapter -VMName Redmond | Add-VMNetworkAdapterAcl -RemoteIPAddress 192.168.0.0/16 -Direction Outbound -Action Meter
```

This example gets virtual network adapters from virtual machine Redmond and adds an ACL to meter outgoing traffic sent to IP subnet 192.168.0.0/16.

## PARAMETERS

### -Action
Specifies the action for the ACL.
Allowed values are **Allow**, **Deny**, and **Meter**.
A metering ACL must be IP-based, i.e.
either -RemoteIPAddress or -LocalIPAddress must be specified.

```yaml
Type: VMNetworkAdapterAclAction
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the ACL is to be created.
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

### -Direction
Specifies the direction of the network traffic to which the ACL is to apply.
Allowed values are **Inbound**, **Outbound**, or **Both**.
. If **Both** is specified, the new ACL entry is added to both the inbound direction and the outbound direction.
In the output of Get-VMNetworkAdapterAcl, the ACL entry appears in both the inbound ACL list and the outbound ACL list.

```yaml
Type: VMNetworkAdapterAclDirection
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalIPAddress
Specifies the local IP address to which the ACL is to apply.
For an inbound packet, this is the destination IP address in the packet header; for an outbound packet, this is the source IP address in the packet header.
It can be either IPv4 or IPv6 address.
It can be either a host address or a subnet address, e.g.
1.2.3.4, 2001::2008, 192.168.1.0/24, or f001:f002:f003:f004::1/64.
The IP address can also be a wildcard, 0.0.0.0/0 for all IPv4 addresses, ::/0 for all IPv6 addresses, or ANY for all IPv4 and IPv6 addresses.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalMacAddress
Specifies the local MAC address to which the ACL is to apply.
For an inbound packet, this is the destination MAC address in the packet header; for an outbound packet, this is the source MAC address in the packet header.
It can be a host MAC address, e.g.
00-ab-00-11-22-33, or a wildcard, ANY, for all MAC addresses.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementOS
Specifies that the ACL is to be applied in the management (i.e.
the parent, or host) operating system.

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

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the ACL to be added.

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

### -RemoteIPAddress
Specifies the remote IP address to which this ACL is to apply.
For an inbound packet, this is the source IP address in the packet header; for an outbound packet, this is the destination IP address in the packet header.
It can be either IPv4 or IPv6 address.
It can be either a host address or a subnet address, e.g.
1.2.3.4, 2001::2008, 192.168.1.0/24, or f001:f002:f003:f004::1/64.the IP address can also be a wildcard, 0.0.0.0/0 for all IPv4 addresses, ::/0 for all IPv6 addresses, or ANY for all IPv4 and IPv6 addresses.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteMacAddress
Specifies the remote MAC address to which this ACL is to apply.
For an inbound packet, this is the source MAC address in the packet header; for an outbound packet, this is the destination MAC address in the packet header.
It can be a host MAC address, e.g.
00-ab-00-11-22-33, or a wildcard, ANY, for all MAC addresses.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine on which the ACL is to apply.

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
Specifies the name of the virtual machine on which the ACL is to apply.

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
Specifies the virtual machine network adapter to which the ACL is to apply.

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
Specifies the name of the virtual machine network adapter to which the ACL is to apply.

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

### Microsoft.Virtualization.Powershell.VMNetworkAdapterAclSetting
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



