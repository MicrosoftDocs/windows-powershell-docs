---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/rename-vmsnapshot?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-VMSnapshot
---

# Rename-VMSnapshot

## SYNOPSIS
Renames a virtual machine checkpoint.

## SYNTAX

### SnapshotName (Default)
```
Rename-VMSnapshot [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-Name] <String> [-VMName] <String> [-NewName] <String> [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SnapshotObject
```
Rename-VMSnapshot [-VMSnapshot] <VMSnapshot> [-NewName] <String> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VM
```
Rename-VMSnapshot [-VM] <VirtualMachine> [-Name] <String> [-NewName] <String> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Rename-VMSnapshot** cmdlet renames a virtual machine checkpoint.

Note: In Windows Server 2012 R2, virtual machine snapshots were renamed to virtual machine checkpoints.
For clarity, this document will refer to virtual machine snapshots as checkpoints.

## EXAMPLES

### Example 1
```
PS C:\> Rename-VMSnapshot -VMName TestVM -Name "Configuration 2" -NewName "Configuration 2: applied all updates"
```

Renames checkpoint Configuration 2 of virtual machine TestVM to Configuration 2: applied all updates.

## PARAMETERS

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
Specifies one or more Hyper-V hosts on which the virtual machine checkpoint is to be renamed.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
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

### -Name
Specifies the name of the virtual machine checkpoint to be renamed.

```yaml
Type: String
Parameter Sets: SnapshotName, VM
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewName
Specifies the name to which the virtual machine checkpoint is to be renamed.

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

### -Passthru
Specifies that a **VMSnapshot** object is to be passed through to the pipeline representing the virtual machine checkpoint to be renamed.

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
Specifies the virtual machine of which the checkpoint is to be renamed.

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
Specifies the name of the virtual machine of which the checkpoint is to be renamed.

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
Specifies the virtual machine checkpoint to be renamed.

```yaml
Type: VMSnapshot
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

### VMSnapshot
If **-PassThru** is specified.

## NOTES

## RELATED LINKS

