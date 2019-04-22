---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Enable-VMResourceMetering
ms.author: kenwith
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 30CFC606-EE24-4001-BD65-16602BB76CE2
---

# Enable-VMResourceMetering

## SYNOPSIS
Collects resource utilization data for a virtual machine or resource pool.

## SYNTAX

### VMName (Default)
```
Enable-VMResourceMetering [-ComputerName <String[]>] [-VMName] <String[]> [<CommonParameters>]
```

### ResourcePool
```
Enable-VMResourceMetering [-ComputerName <String[]>] [-ResourcePoolName] <String>
 [[-ResourcePoolType] <VMResourcePoolType>] [<CommonParameters>]
```

### VMObject
```
Enable-VMResourceMetering [-VM] <VirtualMachine[]> [<CommonParameters>]
```

## DESCRIPTION
The **Enable-VMResourceMetering** cmdlet starts collecting resource utilization data for a virtual machine or resource pool.

You can use the Measure-VM or Measure-VMResourcePool cmdlet to obtain this data.

If resource metering is enabled but no **NetworkAdapterAcls** are configured, Hyper-V configures them to measure total network traffic.
To measure network traffic through an IP range, configure the **NetworkAdapterAcls** for the IP range before calling this cmdlet.
(See Add-VMNetworkAdapterAcl for more information.)

## EXAMPLES

### Example 1
```
PS C:\> Enable-VMResourceMetering -VMName TestVM
```

This example starts collecting resource utilization data on a virtual machine named TestVM.

### Example 2
```
PS C:\> Get-VM TestVM | Enable-VMResourceMetering
PS C:\> Get-VM TestVM | Format-List Name,ResourceMeteringEnabled
```

This example starts collecting resource utilization data on a resource pool named TestResourcePool.
(You can determine whether resource metering is enabled for a resource pool by querying its ResourceMeteringEnabled property.)

### Example 3
```
PS C:\> Enable-VMResourceMetering -ResourcePoolName TestResourcePool -ResourcePoolType Memory
PS C:\> Get-VMResourcePool -Name TestResourcePool -ResourcePoolType Memory | Format-List Name,ResourceMeteringEnabled
```

This example uses two commands that show resource metering being enabled and then obtain the data.
The first command starts collecting resource utilization data for a memory resource pool named TestResourcePool.
(You can determine whether resource metering is enabled for a resource pool by querying its ResourceMeteringEnabled property.) The second command retrieves the data in and formats it as a list.

### Example 4
```
PS C:\> Enable-VMResourceMetering -Name TestResourcePool -ResourcePoolType @("Processor","VHD","Ethernet","Memory")
```

This example begins collecting resource utilization data on multiple resource pools with the name TestResourcePool.

## PARAMETERS

### -ComputerName
Specifies the virtual machine host or hosts on which resource utilization data collection is to be enabled.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName, ResourcePool
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourcePoolName
Specifies the friendly name of the resource pool for which you want to collect resource utilization data.

```yaml
Type: String
Parameter Sets: ResourcePool
Aliases: Name

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ResourcePoolType
Specifies the resource type of the resource pool for which you want to collect resource utilization data.

```yaml
Type: VMResourcePoolType
Parameter Sets: ResourcePool
Aliases: 
Accepted values: Ethernet, Memory, Processor, VHD

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine for which you want to collect resource utilization data.

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
Specifies the friendly name of the virtual machine for which you want to collect resource utilization data.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.HyperV.PowerShell.VirtualMachine[]

### Microsoft.HyperV.PowerShell.VMResourcePoolType

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Measure-VM](./Measure-VM.md)

[Measure-VMResourcePool](./Measure-VMResourcePool.md)

[Disable-VMResourceMetering](./Disable-VMResourceMetering.md)

