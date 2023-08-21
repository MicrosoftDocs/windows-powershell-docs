---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/stop-vm?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Stop-VM

## SYNOPSIS
Shuts down, turns off, or saves a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Stop-VM [-Name] <String[]> [-AsJob] [-ComputerName <String[]>] [-Force] [-Passthru] [-Save] [-TurnOff]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Stop-VM [-VM] <VirtualMachine[]> [-AsJob] [-Force] [-Passthru] [-Save] [-TurnOff] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Stop-VM** cmdlet shuts down, turns off, or saves a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Stop-VM -Name TestVM
```

Shuts down virtual machine TestVM through the guest operating system.

### Example 2
```
PS C:\>Stop-VM -Name VM1 -Force
```

Shuts down virtual machine TestVM through the guest operating system, regardless of any unsaved application data.
Hyper-V gives the guest five minutes to save data, then forces a shutdown.
This shutdown can result in loss of unsaved data.

### Example 3
```
PS C:\>Stop-VM -Name TestVM -TurnOff
```

Turns off virtual machine TestVM.
This operation is equivalent to disconnecting the power from the virtual machine, and can result in loss of unsaved data.

## PARAMETERS

### -AsJob
Specifies that the cmdlet is to be run as a background job.

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
Specifies one or more Hyper-V hosts on which a virtual machine is to be shut down.
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

### -Force
Specifies that the shutdown of the virtual machine is to be forced.
If the virtual machine has applications with unsaved data, the virtual machine has five minutes to save data and shut down.
If the virtual machine is locked, it is shut down immediately.

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

### -Name
Specifies the name of the virtual machine to be shut down.

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

### -Passthru
Specifies that a **Microsoft.Virtualization.Powershell.VirtualMachine** object is to be passed through to the pipeline representing the virtual machine to be shut down.

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

### -Save
Specifies that the virtual machine is to be saved.

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

### -TurnOff
Specifies that the virtual machine is to be turned off.

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
Specifies the virtual machine to be shut down.

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



