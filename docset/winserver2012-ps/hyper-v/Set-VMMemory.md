---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vmmemory?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-VMMemory

## SYNOPSIS
Configures the memory of a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-VMMemory [-VMName] <String[]> [-Buffer <Int32>] [-ComputerName <String[]>]
 [-DynamicMemoryEnabled <Boolean>] [-MaximumAmountPerNumaNodeBytes <Int64>] [-MaximumBytes <Int64>]
 [-MinimumBytes <Int64>] [-Passthru] [-Priority <Int32>] [-ResourcePoolName <String>] [-StartupBytes <Int64>]
```

### UNNAMED_PARAMETER_SET_2
```
Set-VMMemory [-VM] <VirtualMachine[]> [-Buffer <Int32>] [-DynamicMemoryEnabled <Boolean>]
 [-MaximumAmountPerNumaNodeBytes <Int64>] [-MaximumBytes <Int64>] [-MinimumBytes <Int64>] [-Passthru]
 [-Priority <Int32>] [-ResourcePoolName <String>] [-StartupBytes <Int64>]
```

### UNNAMED_PARAMETER_SET_3
```
Set-VMMemory [-VMMemory] <VMMemory[]> [-Buffer <Int32>] [-DynamicMemoryEnabled <Boolean>]
 [-MaximumAmountPerNumaNodeBytes <Int64>] [-MaximumBytes <Int64>] [-MinimumBytes <Int64>] [-Passthru]
 [-Priority <Int32>] [-ResourcePoolName <String>] [-StartupBytes <Int64>]
```

## DESCRIPTION
The **Set-VMMemory** cmdlet configures the memory of a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Set-VMMemory TestVM -DynamicMemoryEnabled $true -MinimumBytes 64MB -StartupBytes 256MB -MaximumBytes 2GB -Priority 80 -Buffer 25
```

Enables dynamic memory on virtual machine TestVM, sets its minimum, startup, and maximum memory, its memory priority, and its buffer.

## PARAMETERS

### -Buffer
Specifies the percentage of memory to reserve as a buffer in the virtual machine to be configured.
Allowed values range from 5 to 2000.

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

### -ComputerName
Specifies one or more Hyper-V hosts on which the memory of a virtual machine is to be configured.
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

### -DynamicMemoryEnabled
Specifies whether dynamic memory is to be enabled on the virtual machine to be configured.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumAmountPerNumaNodeBytes
Specifies the maximum amount of memory per NUMA node in the virtual machine to be configured.

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

### -MaximumBytes
Specifies the maximum amount of memory to be used by a virtual machine which has dynamic memory enabled.

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

### -MinimumBytes
Specifies the minimum amount of memory to be used by a virtual machine which has dynamic memory enabled.

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

### -Passthru
Specifies that a **Microsoft.Virtualization.Powershell.Memory** object is to be passed through to the pipeline representing the virtual machine memory to be configured.

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

### -Priority
Sets the priority for memory availability to this virtual machine relative to other virtual machines on the virtual machine host.
Allowed values range from 0 to 100.

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

### -ResourcePoolName
Specifies the name of the memory resource pool for this virtual machine.

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

### -StartupBytes
Specifies the initial amount of memory to be assigned to a virtual machine with dynamic memory enabled, or the total amount of memory to be assigned to a virtual machine with dynamic memory disabled.

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

### -VM
Specifies the virtual machine whose memory is to be configured.

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

### -VMMemory
Specifies the virtual machine memory to be configured.

```yaml
Type: VMMemory[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine whose memory is to be configured.

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

### Microsoft.Virtualization.Powershell.Memory
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



