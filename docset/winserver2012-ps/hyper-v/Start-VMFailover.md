---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/start-vmfailover?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Start-VMFailover

## SYNOPSIS
Starts failover on a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Start-VMFailover [-VMName] <String[]> [-AsJob] [-ComputerName <String[]>] [-PassThru] [-Prepare] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Start-VMFailover [-VM] <VirtualMachine[]> [-AsJob] [-PassThru] [-AsTest] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Start-VMFailover [-VMRecoverySnapshot] <VMSnapshot> [-AsJob] [-PassThru] [-AsTest] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Start-VMFailover [-VMName] <String[]> [-AsJob] [-ComputerName <String[]>] [-PassThru] [-AsTest] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Start-VMFailover [-VM] <VirtualMachine[]> [-AsJob] [-PassThru] [-Prepare] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_6
```
Start-VMFailover [-VMRecoverySnapshot] <VMSnapshot> [-AsJob] [-PassThru] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Start-VMFailover** cmdlet can be used for the following tasks:

Fail over a Replica virtual machine to a chosen recovery point.

Start a planned failover on a primary virtual machine.

Create a test virtual machine on a Replica virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMSnapshot VM01 -Name Snapshot01 | Start-Failover
```

This example starts failover of a virtual machine named VM01 with recovery point Snapshot01.

Note: Recovery points are stored as snapshots.
To get a list of all snapshots, use the Get-VMSnapshot cmdlet.

### Example 2
```
PS C:\>Start-VMFailover VM01 -AsTest
```

This example starts a test failover of a virtual machine named VM01.

### Example 3
```
PS C:\>Get-VMSnapshot VM01 -Name Snapshot01 | Start-Failover -AsTest
```

Starts a test failover of a virtual machine named VM01 with recovery point Snapshot01.

### Example 4
```
PS C:\>Start-VMFailover -Prepare -VMName VM01  -computername MyPrimary.contoso.com PS C:\>Start-VMFailover -VMName VM01 -computername MyReplica.contoso.com PS C:\>Set-VMReplication -Reverse -VMName VM01 -computername MyReplica.contoso.com PS C:\>Start-VM -VMName VM01 -computername MyReplica.contoso.com
```

This example shows the cmdlets you use to perform a planned failover.
The first command prepares for the planned failover of a primary virtual machine named VM01 by replicating any pending changes.
The second command fails over the Replica virtual machine.
The second command fails over the Replica virtual machine.
The third command switches the Replica virtual machine to a primary virtual machine.
The third command starts the virtual machine that has been switched from a Replica virtual machine to a primary virtual machine.

## PARAMETERS

### -AsJob
Runs the command as a background job.

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

### -AsTest
Creates a test virtual machine using the chosen recovery point.
You can use a test virtual machine to validate a Replica virtual machine.
To stop a test failover, use the Stop-VMFailover cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which failover is to be started.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Specifies that a virtual machine object is to be passed through to the pipeline representing the virtual machine on which failover is to be started.

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

### -Prepare
Starts the planned failover on the primary virtual machine and replicates any pending changes.
To complete the planned failover, use the Set-VMReplication and Start-VM cmdlets as shown in Example 4.

Note: The primary virtual machine must be shut down to prepare it for failover.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine for which failover is to be started.

```yaml
Type: VirtualMachine[]
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine for which failover is to be started.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMRecoverySnapshot
Specifies the recovery snapshot to use during a failover.
(This parameter is not required for a planned failover.)

```yaml
Type: VMSnapshot
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_6
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



