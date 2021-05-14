---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/hyper-v/start-vmfailover?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-VMFailover
---

# Start-VMFailover

## SYNOPSIS
Starts failover on a virtual machine.

## SYNTAX

### VMName (Default)
```
Start-VMFailover [-ComputerName <String[]>] [-VMName] <String[]> [-Prepare] [-AsJob] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### VMName_Test
```
Start-VMFailover [-ComputerName <String[]>] [-VMName] <String[]> [-AsTest] [-AsJob] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### VMObject
```
Start-VMFailover [-VM] <VirtualMachine[]> [-Prepare] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMObject_Test
```
Start-VMFailover [-VM] <VirtualMachine[]> [-AsTest] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMSnapshot_Test
```
Start-VMFailover [-VMRecoverySnapshot] <VMSnapshot> [-AsTest] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMSnapshot
```
Start-VMFailover [-VMRecoverySnapshot] <VMSnapshot> [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Start-VMFailover** cmdlet can be used for the following tasks:

-- Fail over a Replica virtual machine to a chosen recovery point.
-- Start a planned failover on a primary virtual machine.
-- Create a test virtual machine on a Replica virtual machine.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMSnapshot VM01 -Name Snapshot01 | Start-VMFailover
```

This example starts failover of a virtual machine named VM01 with recovery point Snapshot01.

Note: Recovery points are stored as snapshots.
To get a list of all snapshots, use the Get-VMSnapshot cmdlet.

### Example 2
```
PS C:\> Start-VMFailover VM01 -AsTest
```

This example starts a test failover of a virtual machine named VM01.

### Example 3
```
PS C:\> Get-VMSnapshot VM01 -Name Snapshot01 | Start-VMFailover -AsTest
```

Starts a test failover of a virtual machine named VM01 with recovery point Snapshot01.

### Example 4
```
PS C:\> Start-VMFailover -Prepare -VMName VM01  -computername MyPrimary.contoso.com
PS C:\> Start-VMFailover -VMName VM01 -computername MyReplica.contoso.com
PS C:\> Set-VMReplication -Reverse -VMName VM01 -computername MyReplica.contoso.com
PS C:\> Start-VM -VMName VM01 -computername MyReplica.contoso.com
```

This example shows the cmdlets you use to perform a planned failover.
The first command prepares for the planned failover of a primary virtual machine named VM01 by replicating any pending changes.
The second command fails over the Replica virtual machine.
The third command switches the Replica virtual machine to a primary virtual machine.
The fourth command starts the virtual machine that has been switched from a Replica virtual machine to a primary virtual machine.

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
Parameter Sets: VMName_Test, VMObject_Test, VMSnapshot_Test
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
Parameter Sets: VMName, VMName_Test
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
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
Parameter Sets: VMName, VMObject
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
Parameter Sets: VMObject, VMObject_Test
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine for which failover is to be started.

```yaml
Type: String[]
Parameter Sets: VMName, VMName_Test
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMRecoverySnapshot
Specifies the recovery snapshot to use during a failover.
(This parameter is not required for a planned failover.)

```yaml
Type: VMSnapshot
Parameter Sets: VMSnapshot_Test, VMSnapshot
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
None by default; **Microsoft.HyperV.PowerShell.VirtualMachine** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

