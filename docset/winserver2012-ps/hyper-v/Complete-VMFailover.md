---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Complete-VMFailover

## SYNOPSIS
Completes a virtual machine's failover process on the Replica server.
Removes all recovery points on a failed over virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Complete-VMFailover [-VMName] <String[]> [-ComputerName <String[]>] [-PassThru] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Complete-VMFailover [-VM] <VirtualMachine[]> [-PassThru] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Complete-VMFailover** cmdlet completes a virtual machine's failover process on the Replica server.
The recovery point, on which the virtual machine is failed over, is committed and all other recovery points are removed.
Failover cannot be canceled after the recovery points are removed.

## EXAMPLES

### Example 1
```
PS C:\>Complete-VMFailover VM01
```

This command completes the failover process of a virtual machine named VM01, thereby deleting all other recovery points on the server.

### Example 2
```
PS C:\>Complete-VMFailover *
```

This command completes the failover process of all virtual machines on the local host for which the failover process has been started.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the failover process is to be completed.
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
Specifies that an object is to be passed through to the pipeline representing the virtual machine whose failover process is to be completed.

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
Specifies the virtual machine whose failover process is to be completed.

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
Specifies the name of the virtual machine whose failover process is to be completed.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.Virtualization.Powershell.VirtualMachine
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



