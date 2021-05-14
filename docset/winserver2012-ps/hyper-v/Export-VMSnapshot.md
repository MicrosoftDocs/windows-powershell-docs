---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/export-vmsnapshot?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Export-VMSnapshot

## SYNOPSIS
Exports a virtual machine snapshot to disk.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Export-VMSnapshot [-Name] <String[]> [-Path] <String> [-AsJob] [-ComputerName <String[]>] [-Passthru]
 -VMName <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Export-VMSnapshot [-VM] <VirtualMachine[]> [-Path] <String> [-AsJob] [-Passthru] [-Name] <String[]> [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Export-VMSnapshot [-VMSnapshot] <VMSnapshot[]> [-Path] <String> [-AsJob] [-Passthru] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Export-VMSnapshot** cmdlet exports a virtual machine snapshot to disk.

## EXAMPLES

### Example 1
```
PS C:\>Export-VMSnapshot -Name 'Base Image' -VMName TestVM -Path D:\
```

Exports snapshot Base Image of virtual machine TestVM to D:\.

## PARAMETERS

### -AsJob
Specifies that the cmdlet is to be run a background job.

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
Specifies one or more Hyper-V hosts on which the virtual machine snapshot is to be exported.
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

### -Name
Specifies the name of the snapshot to be exported.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Passthru
Specifies that a **VMSnapshot** object is to be passed through to the pipeline representing the snapshot to be exported.

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

### -Path
Specifies the path to the folder into which the snapshot is to be exported.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine of which the snapshot is to be exported.

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
Specifies the name of the virtual machine of which the snapshot is to be exported.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSnapshot
Specifies the snapshot to be exported.

```yaml
Type: VMSnapshot[]
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

### Microsoft.Virtualization.Powershell.Snapshot
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



