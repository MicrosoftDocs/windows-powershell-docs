---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/checkpoint-vm?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Checkpoint-VM

## SYNOPSIS
Creates a snapshot of a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Checkpoint-VM [-Name] <String[]> [[-SnapshotName] <String>] [-AsJob] [-ComputerName <String[]>] [-Passthru]
```

### UNNAMED_PARAMETER_SET_2
```
Checkpoint-VM [-VM] <VirtualMachine[]> [[-SnapshotName] <String>] [-AsJob] [-Passthru]
```

## DESCRIPTION
The **Checkpoint-VM** cmdlet creates a snapshot of a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Checkpoint-VM -Name Test -SnapshotName BeforeInstallingUpdates
```

Checkpoints virtual machine Test, creating a snapshot of it named BeforeInstallingUpdates.

### Example 2
```
PS C:\>Get-VM Test -ComputerName Server1 | Checkpoint-VM
```

Checkpoints virtual machine Test on Hyper-V host Server1.

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
Specifies one or more virtual machine hosts on which the virtual machine snapshot is to be created.
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
Specifies the name of the virtual machine of which a snapshot is to be taken.

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
Specifies that an object is to be passed through to the pipeline representing the virtual machine of which a snapshot is to be taken.

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

### -SnapshotName
Specifies the name of the snapshot to be taken.
If not provided, a combination of the virtual machine's name and a current timestamp is used.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine of which a snapshot is to be taken.

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

## INPUTS

## OUTPUTS

### 
Nothing by default; **Microsoft.Virtualization.Powershell.Snapshot** if **-Passthru** is specified.

## NOTES

## RELATED LINKS



