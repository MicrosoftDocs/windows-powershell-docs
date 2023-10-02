---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/remove-vmsavedstate?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-VMSavedState

## SYNOPSIS
Deletes the saved state of a saved virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-VMSavedState [-VMName] <String[]> [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-VMSavedState [-VM] <VirtualMachine[]>
```

### UNNAMED_PARAMETER_SET_3
```
Remove-VMSavedState [-VMSnapshot] <VMSnapshot>
```

## DESCRIPTION
Deletes the saved state of a saved virtual machine.
Note: data contained in the memory of the virtual machine may be lost; data on its virtual hard disk drives are unaffected.

## EXAMPLES

### Example 1
```
PS C:\>Remove-VMSavedState TestVM
```

Removes the saved state from virtual machine TestVM.

### Example 2
```
PS C:\>Get-VMSnapshot TestVM | Remove-VMSavedState
```

Removes the saved state from all snapshots belonging to virtual machine TestVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual machine saved state is to be deleted.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine whose saved state is to be deleted.

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
Specifies the name of the virtual machine whose saved state is to be deleted.

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
Specifies the snapshot whose saved state is to be deleted.

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

## NOTES

## RELATED LINKS



