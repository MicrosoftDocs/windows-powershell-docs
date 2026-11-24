---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/reset-vmresourcemetering?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Reset-VMResourceMetering
---

# Reset-VMResourceMetering

## SYNOPSIS
Resets the resource utilization data collected by Hyper-V resource metering.

## SYNTAX

### VMName (Default)
```
Reset-VMResourceMetering [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String[]> [<CommonParameters>]
```

### ResourcePool
```
Reset-VMResourceMetering [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-ResourcePoolName] <String> [[-ResourcePoolType] <VMResourcePoolType>] [<CommonParameters>]
```

### VMObject
```
Reset-VMResourceMetering [-VM] <VirtualMachine[]> [<CommonParameters>]
```

## DESCRIPTION
The **Reset-VMResourceMetering** cmdlet resets the resource utilization data collected by Hyper-V resource metering.

When this cmdlet is called, the virtual machine or resource pool resource utilization data collected up to current point of time is deleted.
Hyper-V continues to collect resource utilization data after reset.

## EXAMPLES

### Example 1
```
PS C:\> Reset-VMResourceMetering -VMName TestVM
```

Resets resource utilization data collection on a virtual machine named TestVM.

### Example 2
```
PS C:\> Reset-VMResourceMetering -ResourcePoolName TestResourcePool -ResourcePoolType Memory
```

Resets resource utilization data collection for a single resource pool named TestResourcePool of type Memory.

### Example 3
```
PS C:\> Get-VMResourcePool -ResourcePoolType @("Processor","VHD","Ethernet","Memory") | Reset-VMResourceMetering
```

Resets resource utilization data collection for all supported resource pool types on the virtual machine host.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: VMName, ResourcePool
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more virtual machine hosts for which resource utilization data is to be reset.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName, ResourcePool
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: VMName, ResourcePool
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourcePoolName
Specifies the friendly name of the virtual machine resource pool for which resource utilization data is to be reset.

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
Specifies the resource type of the virtual machine resource pool for which resource utilization data is to be reset.

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
Specifies the virtual machine for which resource utilization data is to be reset.

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
Specifies the friendly name of the virtual machine for which resource utilization data is to be reset.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.HyperV.PowerShell.VirtualMachine[]

### Microsoft.HyperV.PowerShell.VMResourcePoolType

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Measure-VM](./Measure-VM.md)

[Measure-VMResourcePool](./Measure-VMResourcePool.md)
