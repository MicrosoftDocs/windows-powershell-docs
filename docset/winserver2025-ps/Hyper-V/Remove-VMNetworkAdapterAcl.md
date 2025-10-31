---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/remove-vmnetworkadapteracl?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-VMNetworkAdapterAcl
---

# Remove-VMNetworkAdapterAcl

## SYNOPSIS
Removes an ACL applied to the traffic through a virtual network adapter.

## SYNTAX

### VMName (Default)
```
Remove-VMNetworkAdapterAcl [-VMNetworkAdapterName <String>] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-VMName] <String[]>
 -Action <VMNetworkAdapterAclAction> -Direction <VMNetworkAdapterAclDirection> [-LocalIPAddress <String[]>]
 [-LocalMacAddress <String[]>] [-RemoteIPAddress <String[]>] [-RemoteMacAddress <String[]>] [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceObject
```
Remove-VMNetworkAdapterAcl [-VMNetworkAdapter] <VMNetworkAdapterBase[]> -Action <VMNetworkAdapterAclAction>
 -Direction <VMNetworkAdapterAclDirection> [-LocalIPAddress <String[]>] [-LocalMacAddress <String[]>]
 [-RemoteIPAddress <String[]>] [-RemoteMacAddress <String[]>] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ManagementOS
```
Remove-VMNetworkAdapterAcl [-ManagementOS] [-VMNetworkAdapterName <String>] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] -Action <VMNetworkAdapterAclAction>
 -Direction <VMNetworkAdapterAclDirection> [-LocalIPAddress <String[]>] [-LocalMacAddress <String[]>]
 [-RemoteIPAddress <String[]>] [-RemoteMacAddress <String[]>] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMObject
```
Remove-VMNetworkAdapterAcl [-VMNetworkAdapterName <String>] [-VM] <VirtualMachine[]>
 -Action <VMNetworkAdapterAclAction> -Direction <VMNetworkAdapterAclDirection> [-LocalIPAddress <String[]>]
 [-LocalMacAddress <String[]>] [-RemoteIPAddress <String[]>] [-RemoteMacAddress <String[]>] [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObjectParameter
```
Remove-VMNetworkAdapterAcl [-InputObject] <VMNetworkAdapterAclSetting[]> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-VMNetworkAdapterAcl** cmdlet removes an ACL applied to the traffic through a virtual network adapter.

## EXAMPLES

### Example 1
```
PS C:\> Remove-VMNetworkAdapterAcl -VMName Redmond -RemoteIPAddress 0.0.0.0/0 -Direction Both -Action Allow
```

Removes from virtual machine Redmond the ACL allowing any IPv4 traffic sent from or to the virtual machine.

### Example 2
```
PS C:\> Remove-VMNetworkAdapterAcl -VMName Redmond -RemoteIPAddress ::/0 -Direction Both -Action Allow
```

Removes from virtual machine Redmond the ACL that allows any IPv6 traffic sent from and to the virtual machine.

### Example 3
```
PS C:\> Remove-VMNetworkAdapterAcl -VMName Redmond -RemoteMacAddress 03-0f-01-0e-aa-b2 -Direction Both -Action Deny
```

Removes the MAC ACL to prevent virtual machine Redmond from sending traffic to or receiving traffic from a remote device with MAC address 03-0f-01-0e-aa-b2.

### Example 4
```
PS C:\> Get-VMNetworkAdapterAcl -VMName Redmond | Remove-VMNetworkAdapterAcl
```

Retrieves all the port ACLs configured for virtual machine Redmond and pipelines them to Remove-VMNetworkAdapterAcl, which removes all of them from the virtual machine.

## PARAMETERS

### -Action
Specifies the action of the ACL to be removed.
Allowed values are **Allow**, **Deny**, and **Meter**.

```yaml
Type: VMNetworkAdapterAclAction
Parameter Sets: VMName, ResourceObject, ManagementOS, VMObject
Aliases:
Accepted values: Allow, Deny, Meter

Required: True
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

### -ComputerName
Specifies one or more Hyper-V hosts on which the ACL applied to a virtual machine network adapter is to be removed.
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

### -Direction
The direction of the network traffic (from the perspective of the virtual machine) to which the ACL applies.
Allowed values are **Inbound**, **Outbound**, or **Both**.

```yaml
Type: VMNetworkAdapterAclDirection
Parameter Sets: VMName, ResourceObject, ManagementOS, VMObject
Aliases:
Accepted values: Inbound, Outbound, Both

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
Parameter Sets: InputObjectParameter
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -LocalIPAddress
Specifies the local IP address.
It can be either IPv4 or IPv6 address.
It can be either a host address or a subnet address, e.g.
1.2.3.4, 2001::2008, 192.168.1.0/24, or f001:f002:f003:f004::1/64.the IP address can also be a wildcard, 0.0.0.0/0 for all IPv4 addresses, ::/0 for all IPv6 addresses, or ANY for all IPv4 and IPv6 addresses.

```yaml
Type: String[]
Parameter Sets: VMName, ResourceObject, ManagementOS, VMObject
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
Parameter Sets: VMName, ResourceObject, ManagementOS, VMObject
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
Parameter Sets: ManagementOS
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.HyperV.PowerShell.VMNetworkAdapterAclSetting** object is to be passed through to the pipeline representing the ACL to be removed.

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
Parameter Sets: VMName, ResourceObject, ManagementOS, VMObject
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
Parameter Sets: VMName, ResourceObject, ManagementOS, VMObject
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
Parameter Sets: VMObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine from which the ACL is to be removed.

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
Specifies the virtual machine network adapter from which ACL is to be removed.

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
Specifies the name of the virtual machine network adapter from which the ACL is to be removed.

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

By default, this cmdlet doesn't return any output.

### Microsoft.HyperV.PowerShell.VMNetworkAdapterAclSetting

When you use the **PassThru** parameter, this cmdlet returns a **Microsoft.HyperV.PowerShell.VMNetworkAdapterAclSetting** object.

## NOTES

## RELATED LINKS

