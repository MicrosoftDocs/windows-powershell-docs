---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vmnetworkadapterroutingdomainmapping?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VmNetworkAdapterRoutingDomainMapping
---

# Set-VMNetworkAdapterRoutingDomainMapping

## SYNOPSIS
Sets virtual subnets on a routing domain.

## SYNTAX

### VMName (Default)
```
Set-VMNetworkAdapterRoutingDomainMapping [-VMNetworkAdapterName <String>] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-VMName] <String[]> [-RoutingDomainID <Guid>]
 [-RoutingDomainName <String>] [-NewRoutingDomainName <String>] [-IsolationID <Int32[]>]
 [-IsolationName <String[]>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceObject
```
Set-VMNetworkAdapterRoutingDomainMapping [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [-RoutingDomainID <Guid>]
 [-RoutingDomainName <String>] [-NewRoutingDomainName <String>] [-IsolationID <Int32[]>]
 [-IsolationName <String[]>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ManagementOS
```
Set-VMNetworkAdapterRoutingDomainMapping [-ManagementOS] [-VMNetworkAdapterName <String>]
 [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-RoutingDomainID <Guid>] [-RoutingDomainName <String>] [-NewRoutingDomainName <String>]
 [-IsolationID <Int32[]>] [-IsolationName <String[]>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Set-VMNetworkAdapterRoutingDomainMapping [-VMNetworkAdapterName <String>] [-VM] <VirtualMachine[]>
 [-RoutingDomainID <Guid>] [-RoutingDomainName <String>] [-NewRoutingDomainName <String>]
 [-IsolationID <Int32[]>] [-IsolationName <String[]>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObjectParameter
```
Set-VMNetworkAdapterRoutingDomainMapping [-InputObject] <VMNetworkAdapterRoutingDomainSetting>
 [-NewRoutingDomainName <String>] [-IsolationID <Int32[]>] [-IsolationName <String[]>] [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VmNetworkAdapterRoutingDomainMapping** cmdlet sets virtual subnets on a routing domain.

## EXAMPLES

### Example 1: Set a virtual subnet on a routing domain
```
PS C:\> Set-VMNetworkAdapterRoutingDomainMapping -VMName "Gateway01" -VMNetworkAdapterName "Internal NIC" -RoutingDomainID "{5a07361e-6a54-49fc-9210-bfbf14a5c56f}" -IsolationID 6001
```

This command sets the virtual subnet that has the ID 6001 for the specified routing domain.
The command specifies that the routing domain is on the network adapter named Internal NIC that belongs to the multitenant virtual machine named Gateway01.

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
The cmdlet adds the virtual subnets to the routing domain on the Hyper-V hosts that you specify.

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: VMNetworkAdapterRoutingDomainSetting
Parameter Sets: InputObjectParameter
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -IsolationID
Specifies an array of IDs of virtual subnets.
The cmdlet adds the virtual subnets that you specify to the routing domain.
The subnets use VLAN or Hyper-V Network Virtualization.
For more information about isolation IDs, see the **Set-VmNetworkAdapterIsolation** cmdlet.

```yaml
Type: Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsolationName
Specifies an array of names of virtual subnets.
The cmdlet adds the virtual subnets that you specify to the routing domain.
The subnets use VLAN or Hyper-V Network Virtualization.

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
Indicates that the cmdlet operates on the parent partition or host operating system.

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

### -NewRoutingDomainName
Specifies a new name for the routing domain.

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
The cmdlet adds the virtual subnets to the routing domain that you specify.

```yaml
Type: Guid
Parameter Sets: VMName, ResourceObject, ManagementOS, VMObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoutingDomainName
Specifies the name of a routing domain.
The cmdlet adds the virtual subnets to the routing domain that you specify.

```yaml
Type: String
Parameter Sets: VMName, ResourceObject, ManagementOS, VMObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies an array of virtual machine objects.
The cmdlet adds the virtual subnets to the routing domain from the network interfaces that belong to the virtual machines that you specify.
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
The cmdlet adds the virtual subnets to the routing domain from the network interfaces that belong to the virtual machines that you specify.
To obtain a virtual machine object, use the **Get-VM** cmdlet.

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
Specifies an array of virtual network adapters as a **VMNetworkAdapterBase** object.
The cmdlet adds the virtual subnets to the routing domain on the adapters that you specify.
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
The cmdlet adds the virtual subnets to the routing domain on the adapter that you specify.

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

[Add-VmNetworkAdapterRoutingDomainMapping](./Add-VmNetworkAdapterRoutingDomainMapping.md)

[Remove-VMNetworkAdapterRoutingDomainMapping](./Remove-VMNetworkAdapterRoutingDomainMapping.md)

