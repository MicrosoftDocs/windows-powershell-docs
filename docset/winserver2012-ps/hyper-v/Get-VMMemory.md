---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-VMMemory

## SYNOPSIS
Gets the memory of a virtual machine or snapshot.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VMMemory [-VMName] <String[]> [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-VMMemory [-VM] <VirtualMachine[]>
```

### UNNAMED_PARAMETER_SET_3
```
Get-VMMemory [-VMSnapshot] <VMSnapshot>
```

## DESCRIPTION
The **Get-VMMemory** cmdlet gets the memory of a virtual machine or snapshot.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMMemory TestVM
```

Gets the memory object for virtual machine TestVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the memory of a virtual machine or snapshot is to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine whose memory is to be retrieved.

```yaml
Type: VirtualMachine[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine whose memory is to be retrieved.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -VMSnapshot
Specifies the snapshot whose memory is to be retrieved.

```yaml
Type: VMSnapshot
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Virtualization.Powershell.Memory

## NOTES

## RELATED LINKS



