---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vmprocessor?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-VMProcessor

## SYNOPSIS
Configures one or more processors of a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-VMProcessor [-VMName] <String[]> [-CompatibilityForMigrationEnabled <Boolean>]
 [-CompatibilityForOlderOperatingSystemsEnabled <Boolean>] [-ComputerName <String[]>] [-Count <Int64>]
 [-Maximum <Int64>] [-MaximumCountPerNumaNode <Int32>] [-MaximumCountPerNumaSocket <Int32>] [-Passthru]
 [-RelativeWeight <Int32>] [-Reserve <Int64>] [-ResourcePoolName <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Set-VMProcessor [-VM] <VirtualMachine[]> [-CompatibilityForMigrationEnabled <Boolean>]
 [-CompatibilityForOlderOperatingSystemsEnabled <Boolean>] [-Count <Int64>] [-Maximum <Int64>]
 [-MaximumCountPerNumaNode <Int32>] [-MaximumCountPerNumaSocket <Int32>] [-Passthru] [-RelativeWeight <Int32>]
 [-Reserve <Int64>] [-ResourcePoolName <String>]
```

### UNNAMED_PARAMETER_SET_3
```
Set-VMProcessor [-VMProcessor] <VMProcessor[]> [-CompatibilityForMigrationEnabled <Boolean>]
 [-CompatibilityForOlderOperatingSystemsEnabled <Boolean>] [-Count <Int64>] [-Maximum <Int64>]
 [-MaximumCountPerNumaNode <Int32>] [-MaximumCountPerNumaSocket <Int32>] [-Passthru] [-RelativeWeight <Int32>]
 [-Reserve <Int64>] [-ResourcePoolName <String>]
```

## DESCRIPTION
The **Set-VMProcessor** cmdlet configures one or more processors of a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Set-VMProcessor TestVM -Count 2 -Reserve 10 -Maximum 75 -RelativeWeight 200
```

Configures virtual machine TestVM with two virtual processors, a reserve of 10%, a limit of 75%, and a relative weight of 200.

### Example 2
```
PS C:\>Set-VMProcessor TestVM -CompatibilityForMigrationEnabled $true
```

Configures virtual machine TestVM, enabling processor compatibility for live migration.

### Example 3
```
PS C:\>Set-VMProcessor TestVM -CompatibilityForOlderOperatingSystemsEnabled $true
```

Configures virtual machine TestVM, enabling compatibility for running older operating systems.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which processors are to be configured.
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

### -Count
Specifies the number of processors for the virtual machine.

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

### -Maximum
Specifies the maximum percentage of resources available to the virtual machine processor to be configured.
Allowed values range from 0 to 100.

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

### -MaximumCountPerNumaNode
Specifies the maximum number of processors per NUMA node to be configured for the virtual machine.

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

### -MaximumCountPerNumaSocket
Specifies the maximum number of sockets per NUMA node to be configured for the virtual machine.

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

### -Passthru
Specifies that a **Microsoft.Virtualization.Powershell.Processor** is to be passed through to the pipeline representing the processor to be configured.

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

### -RelativeWeight
Specifies the priority for allocating the physical machine's processing power to this virtual machine relative to others.
Allowed values range from 1 to 10000.

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

### -Reserve
Specifies the percentage of processor resources to be reserved for this virtual machine.
Allowed values range from 0 to 100.

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

### -ResourcePoolName
Specifies the name of the processor resource pool to be used.

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

### -VM
Specifies the virtual machine on which the processor is to be configured.

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
Specifies the name of the virtual machine on which the processor is to be configured.

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

### -VMProcessor
Specifies the virtual machine processor to be configured.

```yaml
Type: VMProcessor[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CompatibilityForMigrationEnabled
Specifies whether the virtual processor's features are to be limited for compatibility when migrating the virtual machine to another host.

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

### -CompatibilityForOlderOperatingSystemsEnabled
Specifies whether the virtual processor's features are to be limited for compatibility with older operating systems.

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

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.Virtualization.Powershell.VMNetworkAdapterVlanSetting
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



