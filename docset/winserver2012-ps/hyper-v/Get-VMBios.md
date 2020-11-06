---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-VMBios

## SYNOPSIS
Gets the BIOS of a virtual machine or snapshot.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VMBios [-VMName] <String[]> [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-VMBios [-VM] <VirtualMachine[]>
```

### UNNAMED_PARAMETER_SET_3
```
Get-VMBios [-VMSnapshot] <VMSnapshot>
```

## DESCRIPTION
The **Get-VMBios** cmdlet gets the BIOS of a virtual machine or snapshot.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMBios TestVM
```

Gets the BIOS object for virtual machine TestVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the BIOS of a virtual machine or snapshot is to be retrieved.
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
Specifies the virtual machine whose BIOS is to be retrieved.

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
Specifies the name of the virtual machine whose BIOS is to be retrieved.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMSnapshot
Specifies the virtual machine snapshot whose BIOS is to be retrieved.

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

### Microsoft.Virtualization.Powershell.Bios

## NOTES

## RELATED LINKS



