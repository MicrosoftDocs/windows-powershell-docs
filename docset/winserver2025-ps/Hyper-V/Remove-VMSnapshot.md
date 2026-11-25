---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/remove-vmsnapshot?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-VMSnapshot
---

# Remove-VMSnapshot

## SYNOPSIS
Deletes a virtual machine checkpoint.

## SYNTAX

### SnapshotName (Default)
```
Remove-VMSnapshot [-VMName] <String[]> [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [[-Name] <String[]>] [-IncludeAllChildSnapshots] [-AsJob] [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### VMObject
```
Remove-VMSnapshot [-VM] <VirtualMachine[]> [[-Name] <String[]>] [-IncludeAllChildSnapshots] [-AsJob]
 [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SnapshotObject
```
Remove-VMSnapshot [-VMSnapshot] <VMSnapshot[]> [-IncludeAllChildSnapshots] [-AsJob] [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-VMSnapshot** cmdlet deletes a virtual machine checkpoint.

Note: In Windows Server 2012 R2, virtual machine snapshots were renamed to virtual machine checkpoints.
For clarity, this document will refer to virtual machine snapshots as checkpoints.

## EXAMPLES

### Example 1
```
PS C:\> Get-VM TestVM | Remove-VMSnapshot -Name Experiment*
```

Deletes all checkpoints of virtual machine TestVM whose names starts with Experiment.

### Example 2
```
PS C:\> Get-VMSnapshot -VMName TestVM | Where-Object {$_.CreationTime -lt (Get-Date).AddDays(-90) } | Remove-VMSnapshot
```

Deletes all checkpoints of virtual machine TestVM older than 90 days.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: SnapshotName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which this cmdlet deletes a checkpoint.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: SnapshotName
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
Parameter Sets: SnapshotName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeAllChildSnapshots
Specifies that the checkpoint's children are to be deleted along with the checkpoint.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: IncludeAllChildCheckpoints

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the checkpoint to be deleted.

```yaml
Type: String[]
Parameter Sets: SnapshotName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

```yaml
Type: String[]
Parameter Sets: VMObject
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Passthru
Indicates that this cmdlet returns a **Microsoft.HyperV.PowerShell.VirtualMachine** object that represents the checkpoint that it deletes.

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
Specifies the virtual machine of which the checkpoint is to be deleted.

```yaml
Type: VirtualMachine[]
Parameter Sets: VMObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine of which the checkpoint is to be deleted.

```yaml
Type: String[]
Parameter Sets: SnapshotName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSnapshot
Specifies the checkpoint to be deleted.

```yaml
Type: VMSnapshot[]
Parameter Sets: SnapshotObject
Aliases: VMCheckpoint

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

[Export-VMSnapshot](./Export-VMSnapshot.md)

[Get-VMSnapshot](./Get-VMSnapshot.md)

[Rename-VMSnapshot](./Rename-VMSnapshot.md)

[Restore-VMSnapshot](./Restore-VMSnapshot.md)

[Get-VM](./Get-VM.md)

