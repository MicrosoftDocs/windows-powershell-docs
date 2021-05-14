---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/reset-vmreplicationstatistics?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Reset-VMReplicationStatistics

## SYNOPSIS
Resets the replication statistics of a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Reset-VMReplicationStatistics [-VMName] <String[]> [-ComputerName <String[]>] [-PassThru]
```

### UNNAMED_PARAMETER_SET_2
```
Reset-VMReplicationStatistics [-VM] <VirtualMachine[]> [-PassThru]
```

### UNNAMED_PARAMETER_SET_3
```
Reset-VMReplicationStatistics [-VMReplication] <VMReplication[]> [-PassThru]
```

## DESCRIPTION
The **Reset-VMReplicationStatistics** cmdlet resets the replication statistics of a virtual machine.
Statistics accumulated up to that time are deleted, and replication monitoring begins collecting a new set of statistics.
If replication health was reported as "Warning", then this operation also changes the health to "Normal".

## EXAMPLES

### Example 1
```
PS C:\>Reset-VMReplicationStatistics VM01
```

Resets replication statistics for virtual machine VM01.

### Example 2
```
PS C:\>Get-VMReplication | Reset-VMReplicationStatistics
```

Resets the replication statistics of all replication-enabled virtual machines on the local Hyper-V host.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the replication statistics of a virtual machine are to be reset.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Specifies that a **VMReplication** object is to be passed through to the pipeline representing the replication whose statistics are to be reset.

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
Specifies the virtual machine whose replication statistics are to be reset.

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
Specifies the name of the virtual machine whose replication statistics are to be reset.

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

### -VMReplication
Specifies the virtual machine replication whose replication statistics are to be reset.

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

## INPUTS

## OUTPUTS

### None
Default

### VMReplication
If **-PassThru** is specified.

## NOTES

## RELATED LINKS

