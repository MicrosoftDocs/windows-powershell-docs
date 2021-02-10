---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Set-VM

## SYNOPSIS
Configures a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-VM [-Name] <String[]> [-AllowUnverifiedPaths] [-AutomaticStartAction <StartAction>]
 [-AutomaticStartDelay <Int32>] [-AutomaticStopAction <StopAction>] [-ComputerName <String[]>] [-DynamicMemory]
 [-MemoryMaximumBytes <Int64>] [-MemoryMinimumBytes <Int64>] [-MemoryStartupBytes <Int64>]
 [-NewVMName <String>] [-Notes <String>] [-Passthru] [-ProcessorCount <Int64>] [-SmartPagingFilePath <String>]
 [-SnapshotFileLocation <String>] [-StaticMemory] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-VM [-VM] <VirtualMachine[]> [-AllowUnverifiedPaths] [-AutomaticStartAction <StartAction>]
 [-AutomaticStartDelay <Int32>] [-AutomaticStopAction <StopAction>] [-DynamicMemory]
 [-MemoryMaximumBytes <Int64>] [-MemoryMinimumBytes <Int64>] [-MemoryStartupBytes <Int64>]
 [-NewVMName <String>] [-Notes <String>] [-Passthru] [-ProcessorCount <Int64>] [-SmartPagingFilePath <String>]
 [-SnapshotFileLocation <String>] [-StaticMemory] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-VM** cmdlet configures a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Set-VM -Name TestVM -AutomaticStopAction Shutdown
```

Configures virtual machine TestVM to shut down when the Hyper-V host shuts down.

### Example 2
```
PS C:\>Stop-VM -Name TestVM -Passthru | Set-VM -ProcessorCount 2 -DynamicMemory -MemoryMaximumBytes 2GB -Passthru | Start-VM
```

Stops virtual machine TestVM, sets it to use dynamic memory, sets its maximum amount of memory to 2GB, sets it to use 2 virtual processors, and starts it.

## PARAMETERS

### -AutomaticStartAction
Specifies the action the virtual machine is to take upon start.
Allowed values are **Nothing**, **StartIfRunning**, and **Start**.

```yaml
Type: StartAction
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutomaticStartDelay
Specifies the number of seconds by which the virtual machine's start should be delayed.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutomaticStopAction
Specifies the action the virtual machine is to take when the virtual machine host shuts down.
Allowed values are **TurnOff**, **Save**, and **ShutDown**.

```yaml
Type: StopAction
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual machine is to be configured.
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

### -DynamicMemory
Specifies that the virtual machine is to be configured to use dynamic memory.

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

### -MemoryMaximumBytes
Specifies the maximum amount of memory that the virtual machine is to be allocated.
(Applies only to virtual machines using dynamic memory.)

```yaml
Type: Int64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MemoryMinimumBytes
Specifies the minimum amount of memory that the virtual machine is to be allocated.
(Applies only to virtual machines using dynamic memory.)

```yaml
Type: Int64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MemoryStartupBytes
Specifies the amount of memory that the virtual machine is to be allocated upon startup.
(If the virtual machine does not use dynamic memory, then this is the static amount of memory to be allocated.)

```yaml
Type: Int64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual machine to be configured.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: VMName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NewVMName
Specifies the name to which the virtual machine is to be renamed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the virtual machine to be configured.

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

### -ProcessorCount
Specifies the number of virtual processors for the virtual machine.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SnapshotFileLocation
Specifies the folder in which the virtual machine is to store its snapshot files.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StaticMemory
Specifies the amount of static memory for the virtual machine.

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
Specifies the virtual machine to be configured.

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

### -AllowUnverifiedPaths
Specifies that no error is to be thrown if the specified path is not verified as accessible by the cluster.
This parameter is applicable to clustered virtual machines.

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

### -SmartPagingFilePath
Specifies the folder in which the Smart Paging file is to be stored.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Notes
Specifies notes to be associated with the virtual machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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



