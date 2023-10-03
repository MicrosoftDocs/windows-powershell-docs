---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/resume-vmreplication?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Resume-VMReplication

## SYNOPSIS
Resumes a virtual machine replication that is in a state of Paused, Error, Resynchronization Required, or Suspended.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Resume-VMReplication [-VMName] <String[]> [-AsJob] [-ComputerName <String[]>] [-PassThru] [-Resynchronize]
 [-ResynchronizeStartTime <DateTime>]
```

### UNNAMED_PARAMETER_SET_2
```
Resume-VMReplication [-VM] <VirtualMachine[]> [-AsJob] [-PassThru] [-Resynchronize]
 [-ResynchronizeStartTime <DateTime>]
```

### UNNAMED_PARAMETER_SET_3
```
Resume-VMReplication [-VMReplication] <VMReplication[]> [-AsJob] [-PassThru] [-Resynchronize]
 [-ResynchronizeStartTime <DateTime>]
```

## DESCRIPTION
The **Resume-VMReplication** cmdlet resumes replication of a virtual machine with a replication state of Paused, Error, Resynchronization Required, or Suspended.

## EXAMPLES

### Example 1
```
PS C:\>Resume-VMReplication VM01
```

This example resumes replication of virtual machine VM01.

### Example 2
```
PS C:\>Resume-VMReplication VM01 -Resynchronize
```

This example resynchronizes replication of virtual machine VM01.

### Example 3
```
PS C:\>Resume-VMReplication VM01 -Resynchronize -ResynchronizeStartTime "8/1/2012 05:00 AM"
```

This example schedules the resynchronization of replication for virtual machine VM01 to start at 5:00 AM on August 1, 2012.

### Example 4
```
PS C:\>Resume-Replication *
```

This example resumes replication of all virtual machines for which replication is paused.

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
Specifies one or more Hyper-V hosts on which the virtual machine replication is to be resumed.
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
Specifies that a **VMReplication** object is to be passed through to the pipeline representing the virtual machine replication to be resumed.

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

### -Resynchronize
Specifies that resynchronization is to be started for the virtual machine.
Resynchronization requires significant storage, processor, and network resources.
We recommend running this process during off-peak hours.
Use the **Set-VMReplication** cmdlet to specify whether to automatically resynchronize the virtual machine in the future.

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

### -ResynchronizeStartTime
Specifies when resynchronization should start.
If not specified, resynchronization starts immediately.
You can schedule the resynchronization to start up to 7 days later.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine whose replication is to be resumed.

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
Specifies the name of the virtual machine whose replication is to be resumed.

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
Specifies a virtual machine replication object representing the virtual machine replication to be resumed.

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



