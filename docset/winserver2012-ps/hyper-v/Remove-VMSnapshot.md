---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/remove-vmsnapshot?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-VMSnapshot

## SYNOPSIS
Deletes a virtual machine snapshot.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-VMSnapshot [-VMName] <String[]> [[-Name] <String[]>] [-AsJob] [-ComputerName <String[]>]
 [-IncludeAllChildSnapshots] [-Passthru]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-VMSnapshot [-VM] <VirtualMachine[]> [[-Name] <String[]>] [-AsJob] [-IncludeAllChildSnapshots]
 [-Passthru]
```

### UNNAMED_PARAMETER_SET_3
```
Remove-VMSnapshot [-VMSnapshot] <VMSnapshot[]> [-AsJob] [-IncludeAllChildSnapshots] [-Passthru]
```

## DESCRIPTION
The **Remove-VMSnapshot** deletes a virtual machine snapshot.

## EXAMPLES

### Example 1
```
PS C:\>Get-VM TestVM | Remove-VMSnapshot -Name Experiment*
```

Deletes all snapshots of virtual machine TestVM whose names starts with Experiment.

### Example 2
```
PS C:\>Get-VMSnapshot -VMName TestVM | Where-Object {$_.CreationTime -lt (Get-Date).AddDays(-90) } | Remove-VMSnapshot
```

Deletes all snapshots of virtual machine TestVM older than 90 days.

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
Specifies one or more Hyper-V hosts on which a snapshot is to be deleted.
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

### -IncludeAllChildSnapshots
Specifies that the snapshot's children are to be deleted along with the snapshot.

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
Specifies the name of the snapshot to be deleted.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the snapshot to be deleted.

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
Specifies the virtual machine of which the snapshot is to be deleted.

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
Specifies the name of the virtual machine of which the snapshot is to be deleted.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -VMSnapshot
Specifies the snapshot to be deleted.

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

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.Virtualization.Powershell.VirtualMachine
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



