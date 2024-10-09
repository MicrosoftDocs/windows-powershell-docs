---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/add-vmnetworkadapterroutingdomainmapping?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-VmNetworkAdapterRoutingDomainMapping
---

# Add-VMNetworkAdapterRoutingDomainMapping

## SYNOPSIS
Adds a routing domain and virtual subnets to a virtual network adapter.

## SYNTAX

### VMName (Default)
```
Add-VMNetworkAdapterRoutingDomainMapping [-RoutingDomainID] <Guid> [-RoutingDomainName] <String>
 [-IsolationID] <Int32[]> [[-IsolationName] <String[]>] [-Passthru] [-VMNetworkAdapterName <String>]
 [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-VMName] <String[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceObject
```
Add-VMNetworkAdapterRoutingDomainMapping [-RoutingDomainID] <Guid> [-RoutingDomainName] <String>
 [-IsolationID] <Int32[]> [[-IsolationName] <String[]>] [-Passthru]
 [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ManagementOS
```
Add-VMNetworkAdapterRoutingDomainMapping [-RoutingDomainID] <Guid> [-RoutingDomainName] <String>
 [-IsolationID] <Int32[]> [[-IsolationName] <String[]>] [-Passthru] [-ManagementOS]
 [-VMNetworkAdapterName <String>] [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Add-VMNetworkAdapterRoutingDomainMapping [-RoutingDomainID] <Guid> [-RoutingDomainName] <String>
 [-IsolationID] <Int32[]> [[-IsolationName] <String[]>] [-Passthru] [-VMNetworkAdapterName <String>]
 [-VM] <VirtualMachine[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-VmNetworkAdapterRoutingDomainMapping** cmdlet adds a routing domain and virtual subnets to a virtual network adapter.
The cmdlet adds the information about the routing domain and virtual subnets to connected multitenant virtual machines.

## EXAMPLES

### Example 1: Add a tenant and virtual subnet to a multitenant virtual network
```
PS C:\> Add-VMNetworkAdapterRoutingDomainMapping -VMName "Gateway01" -VMNetworkAdapterName "Internal NIC" -RoutingDomainID "{5a07361e-6a54-49fc-9210-bfbf14a5c56f}" RoutingDomainName "Contoso" -IsolationID 6000 -IsolationName "ContosoGatewayVsid"
```

This command adds a tenant that has the specified routing domain to the virtual network adapter named Internal NIC that belongs to the multitenant virtual machine named Gateway01.
The command also adds the virtual subnet that has the ID 6000 to the virtual network adapter.

## PARAMETERS

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
The cmdlet adds the routing domain and virtual subnet to a virtual network adapter on the Hyper-V hosts that you specify.

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

### -IsolationID
Specifies an array of IDs of virtual subnets.
The cmdlet adds the virtual subnets that you specify to the virtual network adapter.
You can isolate a virtual machine adapter by using virtual local area network (VLAN), Hyper-V Network Virtualization, or a third party virtualization solution.
For more information about isolation IDs, see the **Set-VmNetworkAdapterIsolation** cmdlet.

```yaml
Type: Int32[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsolationName
Specifies an array of names of virtual subnets.
The cmdlet adds the virtual subnets that you specify to the virtual network adapter.
The subnet uses VLAN or Hyper-V Network Virtualization.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementOS
Indicates that the cmdlet operates on the parent or host operating system.

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

### -RoutingDomainID
Specifies the ID of a routing domain.
The ID of a routing domain is a system-assigned GUID.
The cmdlet adds the routing domain that you specify to the virtual network adapter.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoutingDomainName
Specifies the name of a routing domain.
The cmdlet adds the routing domain that you specify to the virtual network adapter.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies an array of virtual machine objects.
The cmdlet adds the routing domain to the network interfaces that belong to the virtual machines that you specify.
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
Specifies an array of friendly names of virtual machines.
The cmdlet adds the routing domain to the network interfaces that belong to the virtual machines that you specify.

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
Specifies an array of virtual network adapter as **VMNetworkAdapterBase** objects.
The cmdlet adds the routing domain on the adapters that you specify.
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
The cmdlet adds the routing domain on adapter that you specify.

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

### Microsoft.HyperV.PowerShell.VMNetworkAdapterRoutingDomainSetting

## NOTES

## RELATED LINKS

[Get-VMNetworkAdapterRoutingDomainMapping](./Get-VMNetworkAdapterRoutingDomainMapping.md)

[Set-VmNetworkAdapterRoutingDomainMapping](./Set-VmNetworkAdapterRoutingDomainMapping.md)

[Remove-VMNetworkAdapterRoutingDomainMapping](./Remove-VMNetworkAdapterRoutingDomainMapping.md)

[Get-VM](./Get-VM.md)

