---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Set-VmNetworkAdapterIsolation
ms.author: v-anbarr
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 44F52076-2253-4C30-94F9-9CC2AFC28EF7
---

# Set-VmNetworkAdapterIsolation

## SYNOPSIS
Modifies isolation settings for a virtual network adapter.

## SYNTAX

### VMName (Default)
```
Set-VmNetworkAdapterIsolation [-IsolationMode <VMNetworkAdapterIsolationMode>]
 [-AllowUntaggedTraffic <Boolean>] [-DefaultIsolationID <Int32>] [-MultiTenantStack <OnOffState>] [-Passthru]
 [-VMNetworkAdapterName <String>] [-ComputerName <String[]>] [-VMName] <String[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ResourceObject
```
Set-VmNetworkAdapterIsolation [-IsolationMode <VMNetworkAdapterIsolationMode>]
 [-AllowUntaggedTraffic <Boolean>] [-DefaultIsolationID <Int32>] [-MultiTenantStack <OnOffState>] [-Passthru]
 [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ManagementOS
```
Set-VmNetworkAdapterIsolation [-IsolationMode <VMNetworkAdapterIsolationMode>]
 [-AllowUntaggedTraffic <Boolean>] [-DefaultIsolationID <Int32>] [-MultiTenantStack <OnOffState>] [-Passthru]
 [-ManagementOS] [-VMNetworkAdapterName <String>] [-ComputerName <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMObject
```
Set-VmNetworkAdapterIsolation [-IsolationMode <VMNetworkAdapterIsolationMode>]
 [-AllowUntaggedTraffic <Boolean>] [-DefaultIsolationID <Int32>] [-MultiTenantStack <OnOffState>] [-Passthru]
 [-VMNetworkAdapterName <String>] [-VM] <VirtualMachine[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VmNetworkAdapterIsolation** cmdlet modifies isolation settings for a virtual network adapter.
You can isolate a virtual machine adapter by using virtual local area network (VLAN), Hyper-V Network Virtualization or a third party virtualization solution.
You can specify the isolation method and modify other settings, which include multitenancy settings.
For more information about multitenancy, see the Add-VmNetworkAdapterRoutingDomainMapping cmdlet.

## EXAMPLES

### Example 1: Set isolation mode for a virtual machine
```
PS C:\> Set-VMNetworkAdapterIsolation -VMName "TSQA01" -AllowUntaggedTraffic $False -IsolationMode NativeVirtualSubnet -MultiTenantStack On
```

This command sets the isolation mode of the virtual machine named TSQA01 to NativeVirtualSubnet, which indicates Hyper-V Network Virtualization.
The virtual machine does not accept untagged traffic, but the **MultitenantStack** parameter has a value of On, so the virtual machine can provide services to multiple tenants.

### Example 2: Set isolation mode and untagged traffic setting for a virtual machine
```
PS C:\> Set-VMNetworkAdapterIsolation -VMName "TSQA01" -AllowUntaggedTraffic $True -IsolationMode VLAN -DefaultIsolationID 1 -MultiTenantStack On
```

This command sets the isolation mode for virtual machine named TSQA01 to be VLAN.
The virtual machine accepts untagged traffic, which is sent and received on VLAN 1, specified by the **DefaultIsolationID** parameter.
Untagged traffic goes to the default compartment in the virtual machine.
Multitenancy is enabled, therefore, the virtual machine receives isolation subnet and routing domain information.

## PARAMETERS

### -AllowUntaggedTraffic
Indicates whether the virtual machine sends and receives untagged traffic.

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

### -ComputerName
Specifies an array of Hyper-V hosts.
The cmdlet modifies isolation settings for virtual machines hosted by the computers that you specify.

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

### -DefaultIsolationID
Specifies the ID of the network for traffic to the default compartment on virtual machines that have multitenancy enabled.

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

### -IsolationMode
Specifies the isolation mode for the adapter.
The acceptable values for this parameter are:

- NativeVirtualSubnet.
Hyper-V Network Virtualization.
- ExternalVirtualSubnet.
A third party network virtualization solution. 
- VLAN.
- None. 

If you specify a value of None, the network adapter uses its default isolation mode.
Set the default isolation mode by using the Set-VMNetworkAdapterVlan cmdlet or the Set-VMNetworkAdapter cmdlet.

```yaml
Type: VMNetworkAdapterIsolationMode
Parameter Sets: (All)
Aliases: 
Accepted values: None, NativeVirtualSubnet, ExternalVirtualSubnet, Vlan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementOS
Indicates that the cmdlet operates on the parent or host operating system.
If you specify this parameter, this cmdlet modifies isolation settings for the parent or host operating system.

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

### -MultiTenantStack
Specifies whether to use multiple isolation IDs for the virtual machine.
The acceptable values for this parameter are:

- On.
Indicate isolation IDs so that the virtual machine provides services to multiple tenants on different isolation subnets. 
- Off.
Do not indicate isolation IDs to virtual machine.

```yaml
Type: OnOffState
Parameter Sets: (All)
Aliases: 
Accepted values: On, Off

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

### -VM
Specifies an array of virtual machine objects.
The cmdlet modifies isolation settings for adapters that belong to the virtual machines that you specify.
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
The cmdlet modifies isolation settings for adapters that belong to the virtual machines that you specify.

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
The cmdlet modifies isolation settings for the adapters that you specify.
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
The cmdlet modifies isolation settings for the adapters that you specify.

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

### None

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMNetworkAdapterIsolation

## NOTES

## RELATED LINKS

[Get-VmNetworkAdapterIsolation](./Get-VmNetworkAdapterIsolation.md)

[Get-VM](./Get-VM.md)

[Get-VMNetworkAdapter](./Get-VMNetworkAdapter.md)

[Set-VMNetworkAdapter](./Set-VMNetworkAdapter.md)

[Set-VMNetworkAdapterVlan](./Set-VMNetworkAdapterVlan.md)

