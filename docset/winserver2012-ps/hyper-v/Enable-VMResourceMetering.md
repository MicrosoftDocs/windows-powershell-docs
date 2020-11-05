---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Enable-VMResourceMetering

## SYNOPSIS
Collects resource utilization data for a virtual machine or resource pool.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Enable-VMResourceMetering [-ResourcePoolName] <String> [[-ResourcePoolType] <VMResourcePoolType>]
 [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Enable-VMResourceMetering [-VMName] <String[]> [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_3
```
Enable-VMResourceMetering [-VM] <VirtualMachine[]>
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
PS C:\>Enable-VMResourceMetering -VMName TestVM
```

This example starts collecting resource utilization data on a virtual machine named TestVM.

### Example 2
```
PS C:\>Get-VM TestVM | Enable-VMResourceMetering
PS C:\>Get-VM TestVM | Format-List Name,ResourceMeteringEnabled
```

This example starts collecting resource utilization data on a resource pool named TestResourcePool.
(You can determine whether resource metering is enabled for a resource pool by querying its ResourceMeteringEnabled property.)

### Example 3
```
PS C:\>Enable-VMResourceMetering -ResourcePoolName TestResourcePool -ResourcePoolType Memory PS C:\>Get-VMResourcePool -Name TestResourcePool -ResourcePoolType Memory | Format-List Name,ResourceMeteringEnabled
```

This example uses two commands that show resource metering being enabled and then obtain the data.
The first command starts collecting resource utilization data for a memory resource pool named TestResourcePool.
(You can determine whether resource metering is enabled for a resource pool by querying its ResourceMeteringEnabled property.) The second command retrieves the data in and formats it as a list.

### Example 4
```
PS C:\>Enable-VMResourceMetering -Name TestResourcePool -ResourcePoolType @("Processor","VHD","Ethernet","Memory")
```

This example begins collecting resource utilization data on multiple resource pools with the name TestResourcePool.

## PARAMETERS

### -ComputerName
Specifies the virtual machine host or hosts on which resource utilization data collection is to be enabled.
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
Specifies the friendly name of the resource pool for which you want to collect resource utilization data.

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
Specifies the resource type of the resource pool for which you want to collect resource utilization data.

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
Specifies the virtual machine for which you want to collect resource utilization data.

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
Specifies the friendly name of the virtual machine for which you want to collect resource utilization data.

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

[Measure-VM](Measure-VM.md)

[Measure-VMResourcePool](Measure-VMResourcePool.md)

[Disable-VMResourceMetering](Disable-VMResourceMetering.md)

