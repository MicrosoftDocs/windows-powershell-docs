---
author: Kateyanne
description: 
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
manager: jasgro
Module Name: Hyper-V
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmnetworkadapterroutingdomainmapping?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMNetworkAdapterRoutingDomainMapping
---

# Get-VMNetworkAdapterRoutingDomainMapping

## SYNOPSIS
Gets members of a routing domain.

## SYNTAX

### VMName (Default)
```
Get-VMNetworkAdapterRoutingDomainMapping [-RoutingDomainID <String>] [-RoutingDomainName <String>]
 [[-VMName] <String[]>] [-VMNetworkAdapterName <String>] [-ComputerName <String[]>] [<CommonParameters>]
```

### VMSnapshot
```
Get-VMNetworkAdapterRoutingDomainMapping [-RoutingDomainID <String>] [-RoutingDomainName <String>]
 [-VMSnapshot] <VMSnapshot> [<CommonParameters>]
```

### ResourceObject
```
Get-VMNetworkAdapterRoutingDomainMapping [-RoutingDomainID <String>] [-RoutingDomainName <String>]
 [-VMNetworkAdapter] <VMNetworkAdapterBase[]> [<CommonParameters>]
```

### ManagementOS
```
Get-VMNetworkAdapterRoutingDomainMapping [-RoutingDomainID <String>] [-RoutingDomainName <String>]
 [-ManagementOS] [-VMNetworkAdapterName <String>] [-ComputerName <String[]>] [<CommonParameters>]
```

### VMObject
```
Get-VMNetworkAdapterRoutingDomainMapping [-RoutingDomainID <String>] [-RoutingDomainName <String>]
 [-VMNetworkAdapterName <String>] [-VM] <VirtualMachine[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VmNetworkAdapterRoutingDomainMapping** cmdlet gets members of a routing domain.

## EXAMPLES

### Example 1: Get members of a routing domain
```
PS C:\>Get-VMNetworkAdapterRoutingDomainMapping -VMName "Gateway01" -VMNetworkAdapterName "Internal NIC"
```

This command gets the members of the routing domain from the network adapter named Internal NIC that belongs to the virtual machine named Gateway01.

## PARAMETERS

### -ComputerName
Specifies an array of Hyper-V hosts.
The cmdlet gets the members of a routing domain on the Hyper-V hosts that you specify.

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

### -RoutingDomainID
Specifies the ID of a routing domain.
The ID of a routing domain is a system-assigned GUID.
The cmdlet gets the members of the routing domain that you specify.

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

### -RoutingDomainName
Specifies the name of a routing domain.
The cmdlet gets the members of the routing domain that you specify.

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

### -VM
Specifies an array of virtual machine objects.
The cmdlet gets the members of the routing domain from the network interfaces that belong to the virtual machines that you specify.
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
Specifies an array of friendly names of virtual machines.
The cmdlet gets the members of the routing domain from the network interfaces that belong to the virtual machines that you specify.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMNetworkAdapter
Specifies an array of virtual network adapters as a **VMNetworkAdapterBase** object.
The cmdlet gets the members of the routing domain on the adapters that you specify.
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
The cmdlet gets the members of the routing domain on the adapter that you specify.

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

### -VMSnapshot
Specifies a snapshot as a **VMSnapshot** object.
The cmdlet gets the members of the routing domain for network adapters that belong to the snapshot that you specify.
To obtain a snapshot object, use the Get-VMSnapshot cmdlet.

```yaml
Type: VMSnapshot
Parameter Sets: VMSnapshot
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-VmNetworkAdapterRoutingDomainMapping](./Add-VmNetworkAdapterRoutingDomainMapping.md)

[Set-VmNetworkAdapterRoutingDomainMapping](./Set-VmNetworkAdapterRoutingDomainMapping.md)

[Remove-VMNetworkAdapterRoutingDomainMapping](./Remove-VMNetworkAdapterRoutingDomainMapping.md)

