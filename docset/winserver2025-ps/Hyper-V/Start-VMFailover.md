---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/start-vmfailover?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-VMFailover
---

# Start-VMFailover

## SYNOPSIS
Starts failover on a virtual machine.

## SYNTAX

### VMName (Default)
```
Start-VMFailover [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String[]> [-Prepare] [-AsJob] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMName_Test
```
Start-VMFailover [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String[]> [-AsTest] [-AsJob] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Start-VMFailover [-VM] <VirtualMachine[]> [-Prepare] [-AsJob] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMObject_Test
```
Start-VMFailover [-VM] <VirtualMachine[]> [-AsTest] [-AsJob] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMSnapshot
```
Start-VMFailover [-VMRecoverySnapshot] <VMSnapshot> [-AsJob] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMSnapshot_Test
```
Start-VMFailover [-VMRecoverySnapshot] <VMSnapshot> [-AsTest] [-AsJob] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Start-VMFailover** cmdlet can be used for the following tasks:

- Fail over a Replica virtual machine to a chosen recovery point.
- Start a planned failover on a primary virtual machine.
- Create a test virtual machine on a Replica virtual machine.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMSnapshot VM01 -Name Snapshot01 | Start-VMFailover
```

This example starts failover of a virtual machine named VM01 with recovery point Snapshot01.

Note: Recovery points are stored as snapshots.
To get a list of all snapshots, use the **Get-VMSnapshot** cmdlet.

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
Runs the cmdlet as a background job.

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
To stop a test failover, use the **Stop-VMFailover** cmdlet.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: VMName, VMName_Test
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which failover is to be started.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName, VMName_Test
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
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: VMName, VMName_Test
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
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
To complete the planned failover, use the **Set-VMReplication** and **Start-VM** cmdlets as shown in Example 4.

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
Parameter Sets: VMSnapshot, VMSnapshot_Test
Aliases: VMRecoveryCheckpoint

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.HyperV.PowerShell.VirtualMachine
If **-PassThru** is specified.

## NOTES

## RELATED LINKS

