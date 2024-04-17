---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/hyper-v/remove-vmnetworkadapterroutingdomainmapping?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-VMNetworkAdapterRoutingDomainMapping
---

# Remove-VMNetworkAdapterRoutingDomainMapping

## SYNOPSIS
Removes a routing domain from a virtual network adapter.

## SYNTAX

### VMName (Default)
```
Remove-VMNetworkAdapterRoutingDomainMapping [-RoutingDomainID <String>] [-RoutingDomainName <String>]
 [-Passthru] [-VMNetworkAdapterName <String>] [-ComputerName <String[]>] [-VMName] <String[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### InputObjectParameter
```
Remove-VMNetworkAdapterRoutingDomainMapping [-InputObject] <VMNetworkAdapterRoutingDomainSetting[]> [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ManagementOS
```
Remove-VMNetworkAdapterRoutingDomainMapping [-RoutingDomainID <String>] [-RoutingDomainName <String>]
 [-Passthru] [-ManagementOS] [-VMNetworkAdapterName <String>] [-ComputerName <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMObject
```
Remove-VMNetworkAdapterRoutingDomainMapping [-RoutingDomainID <String>] [-RoutingDomainName <String>]
 [-Passthru] [-VMNetworkAdapterName <String>] [-VM] <VirtualMachine[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ResourceObject
```
Remove-VMNetworkAdapterRoutingDomainMapping [-RoutingDomainID <String>] [-RoutingDomainName <String>]
 [-Passthru] [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-VmNetworkAdapterRoutingDomainMapping** cmdlet removes a routing domain from a virtual network adapter on a multitenant gateway virtual machine.

## EXAMPLES

### Example 1: Remove a tenant from a multitenant virtual machine
```
PS C:\>Remove-VMNetworkAdapterRoutingDomainMapping -VMName "Gateway01" -VMNetworkAdapterName "Internal NIC" -RoutingDomainID "{5a07361e-6a54-49fc-9210-bfbf14a5c56f}"
```

This command removes the specified routing domain from the virtual network adapter named Internal NIC.
The command specifies that the adapter belongs to the multitenant virtual machine named Gateway01.

## PARAMETERS

### -ComputerName
Specifies an array of Hyper-V hosts.
The cmdlet removes the virtual subnets from the Hyper-V hosts that you specify.

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: VMNetworkAdapterRoutingDomainSetting[]
Parameter Sets: InputObjectParameter
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ManagementOS
Indicates that the cmdlet removes the virtual subnet on the parent partition or host operating system.

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
The cmdlet removes the virtual subnet from the routing domain that you specify.

```yaml
Type: String
Parameter Sets: VMName, ManagementOS, VMObject, ResourceObject
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoutingDomainName
Specifies the name of a routing domain.
The cmdlet removes the virtual subnet from the routing domain that you specify.

```yaml
Type: String
Parameter Sets: VMName, ManagementOS, VMObject, ResourceObject
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies an array of virtual machines.
The cmdlet removes the virtual subnet from the virtual machines that you specify.
To obtain a virtual machine object, use the Get-VM cmdlet.

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
The cmdlet removes the virtual subnet from the virtual machines that you specify.

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
Specifies an array of virtual machine network adapters as **VMNetworkAdapterBase** objects.
The cmdlet removes the virtual subnet for the adapters that you specify.
To obtain a network adapter, use the Get-VMNetworkAdapter cmdlet.

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
The cmdlet removes the virtual subnet for the adapter that you specify.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-VMNetworkAdapterRoutingDomainMapping](./Get-VMNetworkAdapterRoutingDomainMapping.md)

[Add-VmNetworkAdapterRoutingDomainMapping](./Add-VmNetworkAdapterRoutingDomainMapping.md)

[Set-VmNetworkAdapterRoutingDomainMapping](./Set-VmNetworkAdapterRoutingDomainMapping.md)

