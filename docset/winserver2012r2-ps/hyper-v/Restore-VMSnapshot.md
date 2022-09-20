---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/hyper-v/restore-vmsnapshot?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-VMSnapshot
---

# Restore-VMSnapshot

## SYNOPSIS
Restores a virtual machine checkpoint.

## SYNTAX

### SnapshotName (Default)
```
Restore-VMSnapshot [-ComputerName <String[]>] -Name <String> [-VMName] <String> [-AsJob] [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SnapshotObject
```
Restore-VMSnapshot [-VMSnapshot] <VMSnapshot[]> [-AsJob] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VM
```
Restore-VMSnapshot [-VM] <VirtualMachine> -Name <String> [-AsJob] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Restore-VMSnapshot** cmdlet restores a virtual machine checkpoint.

Note: In Windows Server 2012 R2, virtual machine snapshots were renamed to virtual machine checkpoints.
For clarity, this document will refer to virtual machine snapshots as checkpoints.

## EXAMPLES

### Example 1
```
PS C:\>Restore-VMSnapshot -Name 'Base image' -VMName TestVM
Confirm
Are you sure you want to perform this action?
Restore-VMSnapshot will restore checkpoint "Base image".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"): Y
```

Restores checkpoint Base image of virtual machine TestVM.

### Example 2
```
PS C:\>Get-VM | Foreach-Object { $_ | Get-VMSnapshot | Sort CreationTime | Select -Last 1 | Restore-VMSnapshot -Confirm:$false }
```

Applies the most recent checkpoint on all virtual machines with no confirmation prompts.

## PARAMETERS

### -AsJob
Specified that the cmdlet is to be run as a background job.

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
Specifies one or more Hyper-V hosts on which the virtual machine checkpoint is to be restored. 
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: SnapshotName
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

### -Name
Specifies the name of the checkpoint to be restored.

```yaml
Type: String
Parameter Sets: SnapshotName, VM
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **VMSnapshot** is to be passed through to the pipeline representing the checkpoint to be restored.

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
Specifies the virtual machine to be restored.

```yaml
Type: VirtualMachine
Parameter Sets: VM
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine to be restored.

```yaml
Type: String
Parameter Sets: SnapshotName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSnapshot
Specifies an array of **VMSnapshot** objects.
To obtain a **VMSnapshot** object, use the Get-VMSnapshot cmdlet.
The cmdlet restores the virtual machine checkpoints that you specify.

```yaml
Type: VMSnapshot[]
Parameter Sets: SnapshotObject
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
None by default; **VMSnapshot** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

[Get-VMSnapshot](./Get-VMSnapshot.md)

