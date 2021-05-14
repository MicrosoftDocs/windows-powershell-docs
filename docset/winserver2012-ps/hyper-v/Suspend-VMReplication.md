---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/suspend-vmreplication?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Suspend-VMReplication

## SYNOPSIS
Suspends replication of a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Suspend-VMReplication [-VMName] <String[]> [-ComputerName <String[]>] [-PassThru] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Suspend-VMReplication [-VM] <VirtualMachine[]> [-PassThru] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Suspend-VMReplication [-VMReplication] <VMReplication[]> [-PassThru] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Suspend-VMReplication** cmdlet suspends, or pauses, replication of a virtual machine.
To resume replication, use the Resume-VMReplication cmdlet to resume replication.
When replication is resumed, all changes made since replication was suspended will be replicated.

## EXAMPLES

### Example 1
```
PS C:\>Suspend-VMReplication VM01
```

Suspends replication of virtual machine VM01.

### Example 2
```
PS C:\>Suspend-VMReplication *
```

Suspends replication of all virtual machines on the local Hyper-V host.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which replication of a virtual machine is to be suspended.
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
Specifies that a **VMReplication** object is to be passed through to the pipeline representing the replication to be suspended.

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
Specifies the virtual machine whose replication is to be suspended.

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
Specifies the name of the virtual machine whose replication is to be suspended.

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
Specifies the virtual machine replication to be suspended.

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

### VMReplication
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



