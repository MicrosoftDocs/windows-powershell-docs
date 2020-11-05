---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Stop-VMFailover

## SYNOPSIS
Stops failover of a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Stop-VMFailover [-VMName] <String[]> [-AsJob] [-ComputerName <String[]>] [-PassThru]
```

### UNNAMED_PARAMETER_SET_2
```
Stop-VMFailover [-VM] <VirtualMachine[]> [-AsJob] [-PassThru]
```

## DESCRIPTION
The **Stop-VMFailover** cmdlet stops failover of a virtual machine.
If the virtual machine is running, this cmdlet turns the virtual machine off and cancels failover.
For a test failover, this cmdlet stops the test failover and deletes the test virtual machine.
For a planned failover that has been started on a primary virtual machine, this cmdlet cancels that action and restarts replication, which allows you to start the primary virtual machine.

## EXAMPLES

### Example 1
```
PS C:\> Stop-VMFailover VM01
```

This example stops failover for a virtual machine named VM01.

### Example 2
```
PS C:\> Stop-VMFailover *
```

This example stops all running failovers for all the virtual machines on the local Hyper-V host.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.

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

### -ComputerName
Specifies one or more hosts on which to cancel the failover of a virtual machine.
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
Specifies that a VM object is to be passed through to the pipeline representing the virtual machine on which failover is to be stopped.

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
Specifies the virtual machine whose failover you want to cancel.

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
Specifies the name of the virtual machine whose you want to cancel.

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

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.Virtualization.Powershell.VirtualMachine
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



