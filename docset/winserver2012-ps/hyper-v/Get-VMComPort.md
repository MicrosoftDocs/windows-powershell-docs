---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Get-VMComPort

## SYNOPSIS
Gets the COM ports of a virtual machine or snapshot.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VMComPort [-VMName] <String[]> [[-Number] <Int32>] [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-VMComPort [-VM] <VirtualMachine[]> [[-Number] <Int32>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-VMComPort [-VMSnapshot] <VMSnapshot> [[-Number] <Int32>]
```

## DESCRIPTION
The **Get-VMComPort** cmdlet gets the COM ports of a virtual machine or snapshot.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMComPort TestVM
```

Gets all COM ports associated with virtual machine TestVM.

### Example 2
```
PS C:\>Get-VMComPort TestVM -Number 2
```

Gets the second COM port associated with virtual machine TestVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the COM ports of a virtual machine or snapshot are to be retrieved.
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

### -Number
Specifies the Id (1 or 2) of the COM ports to be retrieved.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine whose COM ports are to be retrieved.

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
Specifies the name of the virtual machine whose COM ports are to be retrieved.

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
Specifies the snapshot whose COM ports are to be retrieved.

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

### Microsoft.Virtualization.Powershell.ComPort

## NOTES

## RELATED LINKS

[00000000-0000-0000-0000-000000000000](00000000-0000-0000-0000-000000000000)

