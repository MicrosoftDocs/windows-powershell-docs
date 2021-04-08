---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmidecontroller?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VMIdeController

## SYNOPSIS
Gets the IDE controllers of a virtual machine or snapshot.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VMIdeController [-VMName] <String[]> [[-ControllerNumber] <Int32>] [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-VMIdeController [-VM] <VirtualMachine[]> [[-ControllerNumber] <Int32>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-VMIdeController [-VMSnapshot] <VMSnapshot> [[-ControllerNumber] <Int32>]
```

## DESCRIPTION
The **Get-VMIdeController** cmdlet gets the IDE controllers of a virtual machine or snapshot.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMIdeController TestVM
```

Gets all IDE controllers belonging to virtual machine TestVM.

### Example 2
```
PS C:\>Get-VMIdeController TestVM -ControllerNumber 0
```

Gets the first IDE controller belonging to virtual machine TestVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the IDE controllers of a virtual machine or snapshot are to be retrieved.
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

### -ControllerNumber
Specifies the number of the IDE controller to be retrieved.
Allowed values are 0 and 1.

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
Specifies the virtual machine whose IDE controllers are to be retrieved.

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
Specifies the name of the virtual machine whose IDE controllers are to be retrieved.

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
Specifies the snapshot whose IDE controllers are to be retrieved.

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

### Microsoft.Virtualization.Powershell.IDEController

## NOTES

## RELATED LINKS



