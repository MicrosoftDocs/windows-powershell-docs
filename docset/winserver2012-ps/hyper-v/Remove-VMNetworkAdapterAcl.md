---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/remove-vmnetworkadapteracl?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-VMNetworkAdapterAcl

## SYNOPSIS
Removes an ACL applied to the traffic through a virtual network adapter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-VMNetworkAdapterAcl [-VMName] <String[]> [-ComputerName <String[]>] [-LocalIPAddress <String[]>]
 [-LocalMacAddress <String[]>] [-Passthru] [-RemoteIPAddress <String[]>] [-RemoteMacAddress <String[]>]
 [-VMNetworkAdapterName <String>] -Action <VMNetworkAdapterAclAction> -Direction <VMNetworkAdapterAclDirection>
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-VMNetworkAdapterAcl [-ComputerName <String[]>] [-LocalIPAddress <String[]>]
 [-LocalMacAddress <String[]>] [-Passthru] [-RemoteIPAddress <String[]>] [-RemoteMacAddress <String[]>]
 [-VMNetworkAdapterName <String>] -Action <VMNetworkAdapterAclAction> -Direction <VMNetworkAdapterAclDirection>
 [-ManagementOS] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Remove-VMNetworkAdapterAcl [-VM] <VirtualMachine[]> [-LocalIPAddress <String[]>] [-LocalMacAddress <String[]>]
 [-Passthru] [-RemoteIPAddress <String[]>] [-RemoteMacAddress <String[]>] [-VMNetworkAdapterName <String>]
 -Action <VMNetworkAdapterAclAction> -Direction <VMNetworkAdapterAclDirection> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Remove-VMNetworkAdapterAcl [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [-LocalIPAddress <String[]>]
 [-LocalMacAddress <String[]>] [-Passthru] [-RemoteIPAddress <String[]>] [-RemoteMacAddress <String[]>]
 -Action <VMNetworkAdapterAclAction> -Direction <VMNetworkAdapterAclDirection> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Remove-VMNetworkAdapterAcl [-InputObject] <VMNetworkAdapterAclSetting[]> [-Passthru] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-VMNetworkAdapterAcl** cmdlet removes an ACL applied to the traffic through a virtual network adapter.

## EXAMPLES

### Example 1
```
PS C:\>Remove-VMNetworkAdapterAcl -VMName Redmond -RemoteIPAddress 0.0.0.0/0 -Direction Both -Action Allow
```

Removes from virtual machine Redmond the ACL allowing any IPv4 traffic sent from or to the virtual machine.

### Example 2
```
PS C:\>Remove-VMNetworkAdapterAcl -VMName Redmond -RemoteIPAddress ::/0 -Direction Both -Action Allow
```

Removes from virtual machine Redmond the ACL that allows any IPv6 traffic sent from and to the virtual machine.

### Example 3
```
PS C:\>Remove-VMNetworkAdapterAcl -VMName Redmond -RemoteMacAddress 03-0f-01-0e-aa-b2 -Direction Both -Action Deny
```

Removes the MAC ACL to prevent virtual machine Redmond from sending traffic to or receiving traffic from a remote device with MAC address 03-0f-01-0e-aa-b2.

### Example 4
```
PS C:\>Get-VMNetworkAdapterAcl -VMName Redmond | Remove-VMNetworkAdapterAcl
```

Retrieves all the port ACLs configured for virtual machine Redmond and pipelines them to Remove-VMNetworkAdapterAcl, which removes all of them from the virtual machine.

## PARAMETERS

### -Action
Specifies the action of the ACL to be removed.
Allowed values are **Allow**, **Deny**, and **Meter**.

```yaml
Type: VMNetworkAdapterAclAction
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the ACL applied to a virtual machine network adapter is to be removed.
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
The direction of the network traffic (from the perspective of the virtual machine) to which the ACL applies.
Allowed values are **Inbound**, **Outbound**, or **Both**.

```yaml
Type: VMNetworkAdapterAclDirection
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the ACL to be removed.

```yaml
Type: VMNetworkAdapterAclSetting[]
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -LocalIPAddress
Specifies the local IP address.
It can be either IPv4 or IPv6 address.
It can be either a host address or a subnet address, e.g.
1.2.3.4, 2001::2008, 192.168.1.0/24, or f001:f002:f003:f004::1/64.the IP address can also be a wildcard, 0.0.0.0/0 for all IPv4 addresses, ::/0 for all IPv6 addresses, or ANY for all IPv4 and IPv6 addresses.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalMacAddress
Specifies the local MAC address (e.g.
00-ab-00-11-22-33).
Use the wildcard **ANY** to specify all MAC addresses.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementOS
Specifies that the ACL is to be removed from the management (e.g.
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
Specifies that a **Microsoft.Virtualization.Powershell.VMNetworkAdapterAclSetting** object is to be passed through to the pipeline representing the ACL to be removed.

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
Specifies the remote IP address.
. It can be either IPv4 or IPv6 address.
It can be either a host address or a subnet address, e.g.
1.2.3.4, 2001::2008, 192.168.1.0/24, or f001:f002:f003:f004::1/64.
the IP address can also be a wildcard, 0.0.0.0/0 for all IPv4 addresses, ::/0 for all IPv6 addresses, or ANY for all IPv4 and IPv6 addresses.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteMacAddress
Specifies the remote MAC address.
. It can be a host MAC address, e.g.
00-ab-00-11-22-33, or a wildcard, ANY, for all MAC addresses.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine from which the ACL is to be removed.

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
Specifies the name of the virtual machine from which the ACL is to be removed.

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
Specifies the virtual machine network adapter from which ACL is to be removed.

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
Specifies the name of the virtual machine network adapter from which the ACL is to be removed.

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

### 
None by default, **Microsoft.Virtualization.Powershell.VMNetworkAdapterAclSetting** if **-PassThru** is specified.

## NOTES

## RELATED LINKS



