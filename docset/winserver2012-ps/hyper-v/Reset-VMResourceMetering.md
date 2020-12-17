---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Reset-VMResourceMetering

## SYNOPSIS
Resets the resource utilization data collected by Hyper-V resource metering.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Reset-VMResourceMetering [-ResourcePoolName] <String> [[-ResourcePoolType] <VMResourcePoolType>]
 [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Reset-VMResourceMetering [-VMName] <String[]> [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_3
```
Reset-VMResourceMetering [-VM] <VirtualMachine[]>
```

## DESCRIPTION
The **Reset-VMResourceMetering** cmdlet resets the resource utilization data collected by Hyper-V resource metering.

When this cmdlet is called, the virtual machine or resource pool resource utilization data collected up to current point of time is deleted.
Hyper-V continues to collect resource utilization data after reset.

## EXAMPLES

### Example 1
```
PS C:\>Reset-VMResourceMetering -VMName TestVM
```

Resets resource utilization data collection on a virtual machine named TestVM.

### Example 2
```
PS C:\>Reset-VMResourceMetering -ResourcePoolName TestResourcePool -ResourcePoolType Memory
```

Resets resource utilization data collection for a single resource pool named TestResourcePool of type Memory.

### Example 3
```
PS C:\>Get-VMResourcePool -ResourcePoolType @("Processor","VHD","Ethernet","Memory") | Reset-VMResourceMetering
```

Resets resource utilization data collection for all supported resource pool types on the virtual machine host.

## PARAMETERS

### -ComputerName
Specifies one or more virtual machine hosts for which resource utilization data is to be reset.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourcePoolName
Specifies the friendly name of the virtual machine resource pool for which resource utilization data is to be reset.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -ResourcePoolType
Specifies the resource type of the virtual machine resource pool for which resource utilization data is to be reset.

```yaml
Type: VMResourcePoolType
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine for which resource utilization data is to be reset.

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
Specifies the friendly name of the virtual machine for which resource utilization data is to be reset.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.HyperV.PowerShell.VirtualMachine[]

### Microsoft.HyperV.PowerShell.VMResourcePoolType

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Measure-VM](./Measure-VM.md)

[Measure-VMResourcePool](./Measure-VMResourcePool.md)
