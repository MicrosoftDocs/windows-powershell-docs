---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/stop-vmreplication?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Stop-VMReplication

## SYNOPSIS
Cancels an ongoing virtual machine resynchronization.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Stop-VMReplication [-VMName] <String[]> [-ComputerName <String[]>] [-PassThru] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Stop-VMReplication [-VM] <VirtualMachine[]> [-PassThru] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Stop-VMReplication [-VMReplication] <VMReplication[]> [-PassThru] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Stop-VMReplication** cmdlet cancels an ongoing virtual machine resynchronization.

## EXAMPLES

### Example 1
```
PS C:\>Stop-VMReplication *
```

Stops all ongoing replications of virtual machines on the local Hyper-V server.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the ongoing virtual machine resynchronization is to be stopped.
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
Specifies that an object is to be passed through to the pipeline representing the virtual machine on which the ongoing virtual machine resynchronization is to be stopped.

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
Specifies the virtual machine whose resynchronization is to be stopped.

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
Specifies the name of the virtual machine whose resynchronization is to be stopped.

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
Specifies the resynchronization to be stopped.

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

### Microsoft.Virtualization.Powershell.VirtualMachine
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



