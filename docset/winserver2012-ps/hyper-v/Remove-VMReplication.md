---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/remove-vmreplication?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-VMReplication

## SYNOPSIS
Removes the replication relationship of a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-VMReplication [-VMName] <String[]> [-ComputerName <String[]>] [-PassThru]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-VMReplication [-VM] <VirtualMachine[]> [-PassThru]
```

### UNNAMED_PARAMETER_SET_3
```
Remove-VMReplication [-VMReplication] <VMReplication[]> [-PassThru]
```

## DESCRIPTION
The **Remove-VMReplication** removes the replication relationship of a virtual machine.
Replication must be removed independently from both the primary and Replica virtual machines.
Removing replication on a Replica virtual machine does not delete the Replica virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Remove-VMReplication VM01
```

This example removes the replication relationship of virtual machine VM01.

### Example 2
```
PS C:\>Remove-VMReplication *
```

This example removes the replication relationships from all replica-enabled virtual machines on the local Hyper-V host.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the replication relationship of a virtual machine is to be removed.
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

### -PassThru
Specifies that a **VMReplication** object is to be passed through to the pipeline representing the virtual machine for which the replication relationship will be removed.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine for which the replication relationship is to be removed.

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
Specifies the name of the virtual machine for which the replication relationship is to be removed.

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

### -VMReplication
Specifies a virtual machine replication object associated with the virtual machine whose replication relationship is to be removed.

```yaml
Type: VMReplication[]
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

### None
Default

### VMReplication
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



