---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Disable-VMResourceMetering

## SYNOPSIS
Disables collection of resource utilization data for a virtual machine or resource pool.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Disable-VMResourceMetering [-ResourcePoolName] <String> [[-ResourcePoolType] <VMResourcePoolType>]
 [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Disable-VMResourceMetering [-VMName] <String[]> [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_3
```
Disable-VMResourceMetering [-VM] <VirtualMachine[]>
```

## DESCRIPTION
The **Disable-VMResourceMetering** cmdlet disables collection of resource utilization data for a virtual machine or resource pool.

Calling this cmdlet stops collection of data and deletes data collected up to the point of the call.

After the call, Measure-VM and Measure-VMResourcePool are not usable.

## EXAMPLES

### Example 1
```
PS C:\>Disable-VMResourceMetering -VMName TestVM
```

Disables collection of resource utilization data on a virtual machine named TestVM.

### Example 2
```
PS C:\>Get-VM Test* | Disable-VMResourceMetering
```

Disables collection of resource utilization data on a set of virtual machines whose names begin with the string Test.

### Example 3
```
PS C:\>Disable-VMResourceMetering -ResourcePoolName TestResourcePool -ResourcePoolType Memory
```

Disables collection of resource utilization data collection on a resource pool named TestResourcePool of type Memory.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which resource utilization data collection is to be disabled.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourcePoolName
Specifies the friendly name of the resource pool on which resource utilization data collection is to be disabled.

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
Specifies the resource type of the resource pool on which resource utilization data collection is to be disabled.

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
Specifies the virtual machine on which resource utilization data collection is to be disabled.

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
Specifies the friendly name of the virtual machine on which resource utilization data collection is to be disabled.

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

## NOTES

## RELATED LINKS

[Measure-VM](1e88b99a-9b5e-43ce-929f-7608ee7a7620)

[Measure-VMResourcePool](692df375-67a3-4945-8590-3cccab788f35)

[Enable-VMResourceMetering](30cfc606-ee24-4001-bd65-16602bb76ce2)

