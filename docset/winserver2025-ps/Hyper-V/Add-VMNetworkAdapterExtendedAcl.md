---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/add-vmnetworkadapterextendedacl?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-VMNetworkAdapterExtendedAcl
---

# Add-VMNetworkAdapterExtendedAcl

## SYNOPSIS
Creates an extended ACL for a virtual network adapter.

## SYNTAX

### VMName (Default)
```
Add-VMNetworkAdapterExtendedAcl [-Action] <VMNetworkAdapterExtendedAclAction>
 [-Direction] <VMNetworkAdapterExtendedAclDirection> [[-LocalIPAddress] <String>] [[-RemoteIPAddress] <String>]
 [[-LocalPort] <String>] [[-RemotePort] <String>] [[-Protocol] <String>] [-Weight] <Int32>
 [-Stateful <Boolean>] [-IdleSessionTimeout <Int32>] [-IsolationID <Int32>] [-Passthru]
 [-VMNetworkAdapterName <String>] [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-VMName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceObject
```
Add-VMNetworkAdapterExtendedAcl [-Action] <VMNetworkAdapterExtendedAclAction>
 [-Direction] <VMNetworkAdapterExtendedAclDirection> [[-LocalIPAddress] <String>] [[-RemoteIPAddress] <String>]
 [[-LocalPort] <String>] [[-RemotePort] <String>] [[-Protocol] <String>] [-Weight] <Int32>
 [-Stateful <Boolean>] [-IdleSessionTimeout <Int32>] [-IsolationID <Int32>] [-Passthru]
 [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ManagementOS
```
Add-VMNetworkAdapterExtendedAcl [-Action] <VMNetworkAdapterExtendedAclAction>
 [-Direction] <VMNetworkAdapterExtendedAclDirection> [[-LocalIPAddress] <String>] [[-RemoteIPAddress] <String>]
 [[-LocalPort] <String>] [[-RemotePort] <String>] [[-Protocol] <String>] [-Weight] <Int32>
 [-Stateful <Boolean>] [-IdleSessionTimeout <Int32>] [-IsolationID <Int32>] [-Passthru] [-ManagementOS]
 [-VMNetworkAdapterName <String>] [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Add-VMNetworkAdapterExtendedAcl [-Action] <VMNetworkAdapterExtendedAclAction>
 [-Direction] <VMNetworkAdapterExtendedAclDirection> [[-LocalIPAddress] <String>] [[-RemoteIPAddress] <String>]
 [[-LocalPort] <String>] [[-RemotePort] <String>] [[-Protocol] <String>] [-Weight] <Int32>
 [-Stateful <Boolean>] [-IdleSessionTimeout <Int32>] [-IsolationID <Int32>] [-Passthru]
 [-VMNetworkAdapterName <String>] [-VM] <VirtualMachine[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-VMNetworkAdapterExtendedAcl** cmdlet creates an extended access control list (ACL) for a virtual network adapter.
The ACL allows or denies access to a virtual machine network adapter for network packets based on source IP address, destination IP address, protocol, source port, and destination port.

## EXAMPLES

### Example 1: Create an ACL for Remote Desktop Protocol
```
PS C:\> Add-VMNetworkAdapterExtendedAcl -VMName "TSQA01" -Action Allow -Direction Inbound -LocalPort "3389" -Protocol "TCP" -Weight 10 -Stateful $True
```

This command creates a stateful inbound ACL that allows a remote device to connect to the virtual machine on port 3389, which is the port for Remote Desktop Protocol.

### Example 2: Create an ACL to initiate a connection with timeout
```
PS C:\> Add-VMNetworkAdapterExtendedAcl -VMName "TSQA03" -Action Allow -Direction Outbound -RemotePort "80" -Protocol "TCP" -Weight 100 -Timeout 3600 -Stateful $True
```

This command creates a stateful ACL that allows outbound packets to a remote device by using TCP.
If there is no activity for 3600 seconds, the connection times out.

## PARAMETERS

### -Action
Specifies the action for the ACL.
The acceptable values for this parameter are:

- Allow
- Deny

```yaml
Type: VMNetworkAdapterExtendedAclAction
Parameter Sets: (All)
Aliases:
Accepted values: Allow, Deny

Required: True
Position: 1
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

### -ComputerName
Specifies an array of Hyper-V hosts.
The cmdlet adds the ACL to the network adapters on the Hyper-V hosts that you specify.

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

### -Direction
Specifies the direction of network traffic, from the perspective of the virtual machine, to which the ACL applies.
The cmdlet adds an ACL that has the value that you specify.
The acceptable values for this parameter are:

- Inbound
- Outbound

 If you run the **Get-VMNetworkAdapterExtendedAcl** cmdlet, the entry that you create appears in both the inbound ACL and the outbound ACL.

```yaml
Type: VMNetworkAdapterExtendedAclDirection
Parameter Sets: (All)
Aliases:
Accepted values: Inbound, Outbound

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdleSessionTimeout
Specifies a time-out period, in seconds, for idle sessions.

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

### -IsolationID
Specifies an ID of a virtual subnet.
The cmdlet adds an ACL that applies to traffic on the isolated network that you specify.
The subnet uses virtual local area network (VLAN) or Hyper-V Network Virtualization.
For more information about isolation IDs, see the **Set-VmNetworkAdapterIsolation** cmdlet.

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

### -LocalIPAddress
Specifies the local IP address for the ACL.
For an inbound packet, the local address is the destination IP address.
For an outbound packet, the local address is the source IP address.
You can specify a host address or a subnet address, or specify a wildcard, such as 0.0.0.0/0 for all IPv4 addresses, ::/0 for all IPv6 addresses, or ANY for all IPv4 and IPv6 addresses.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalPort
Specifies the local port for the ACL. A port range format can also be used (i.e. "49152-49182", for example).
For an inbound TCP or UDP packet, the local port is the destination port.
For an outbound packet, the local port is the source port.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementOS
Indicates that the cmdlet operates on the parent or host operating system.
If you specify this parameter, this cmdlet creates an ACL that applies to the parent or host operating system.

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

### -Passthru
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

### -Protocol
Specifies the protocol that the ACL applies to.
The acceptable values for this parameter are:

- TCP
- UDP
- an integer IP protocol ID (**use 1 for ICMP**)

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteIPAddress
Specifies the local IP address for the ACL.
For an inbound packet, the remote address is the source IP address.
For an outbound packet, the remote address is the destination IP address.
You can specify a host address or a subnet address, or specify a wildcard, such as 0.0.0.0/0 for all IPv4 addresses, ::/0 for all IPv6 addresses, or ANY for all IPv4 and IPv6 addresses.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemotePort
Specifies the remote port for the ACL. A port range format can also be used (i.e. "49152-49182", for example).
For an inbound TCP or UDP packet, the remote port is the source port.
For an outbound packet, the remote port is the destination port.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stateful
Indicates whether the ACL applies to packets in both directions of the same session.
If you specify a value of $True, the ACL applies to a return packet even though that packet has the opposite direction with respect to the ACL.

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

### -VM
Specifies an array of virtual machine objects.
The cmdlet adds an ACL for the virtual machines that you specify.
To obtain a virtual machine object, use the **Get-VM** cmdlet.

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
Specifies an array of names of virtual machines.
The cmdlet adds an ACL for the virtual machines that you specify.

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
Specifies an array VM network adapters as **VMNetworkAdapterBase** objects.
The cmdlet adds an ACL to the adapters that you specify.
To obtain a network adapter, use the **Get-VMNetworkAdapter** cmdlet.

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
Specifies the name of a virtual network adapter.
The cmdlet adds an ACL to the adapter that you specify.

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

### -Weight
Specifies the weight of an ACL entry.
Larger weight values apply first, and once an ACL entry applies to a packet, other entries are no longer relevant for that packet.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: 8
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

### None

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMNetworkAdapterExtendedAclSetting

## NOTES

## RELATED LINKS

[Get-VMNetworkAdapterExtendedAcl](./Get-VMNetworkAdapterExtendedAcl.md)

[Remove-VMNetworkAdapterExtendedAcl](./Remove-VMNetworkAdapterExtendedAcl.md)

[Get-VM](./Get-VM.md)

[Set-VmNetworkAdapterIsolation](./Set-VmNetworkAdapterIsolation.md)

