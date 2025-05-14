---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/disable-vmresourcemetering?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-VMResourceMetering
---

# Disable-VMResourceMetering

## SYNOPSIS
Disables collection of resource utilization data for a virtual machine or resource pool.

## SYNTAX

### VMName (Default)
```
Disable-VMResourceMetering [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-VMName] <String[]> [<CommonParameters>]
```

### ResourcePool
```
Disable-VMResourceMetering [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-ResourcePoolName] <String> [[-ResourcePoolType] <VMResourcePoolType>]
 [<CommonParameters>]
```

### VMObject
```
Disable-VMResourceMetering [-VM] <VirtualMachine[]> [<CommonParameters>]
```

## DESCRIPTION
The **Disable-VMResourceMetering** cmdlet disables collection of resource utilization data for a virtual machine or resource pool.

Calling this cmdlet stops collection of data and deletes data collected up to the point of the call.

After the call, Measure-VM and Measure-VMResourcePool are not usable.

## EXAMPLES

### Example 1
```
PS C:\> Disable-VMResourceMetering -VMName TestVM
```

Disables collection of resource utilization data on a virtual machine named TestVM.

### Example 2
```
PS C:\> Get-VM Test* | Disable-VMResourceMetering
```

Disables collection of resource utilization data on a set of virtual machines whose names begin with the string Test.

### Example 3
```
PS C:\> Disable-VMResourceMetering -ResourcePoolName TestResourcePool -ResourcePoolType Memory
```

Disables collection of resource utilization data on a resource pool named TestResourcePool of type Memory.

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
Specifies one or more Hyper-V hosts on which resource utilization data collection is to be disabled.
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
Specifies the friendly name of the resource pool on which resource utilization data collection is to be disabled.

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
Specifies the resource type of the resource pool on which resource utilization data collection is to be disabled.

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
Specifies the virtual machine on which resource utilization data collection is to be disabled.

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
Specifies the friendly name of the virtual machine on which resource utilization data collection is to be disabled.

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

## NOTES

## RELATED LINKS

[Measure-VM](./Measure-VM.md)

[Measure-VMResourcePool](./Measure-VMResourcePool.md)

[Enable-VMResourceMetering](./Enable-VMResourceMetering.md)

