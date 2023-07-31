---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 06/21/2023
online version: https://learn.microsoft.com/powershell/module/hyper-v/remove-vhdsnapshot?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-VHDSnapshot
---

# Remove-VHDSnapshot

## SYNOPSIS
Removes a checkpoint from a VHD set file.

## SYNTAX

### Path (Default)

```
Remove-VHDSnapshot [-Path] <String[]> [-PersistReferencePoint] -SnapshotId <Guid[]> [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VHDSnapshot

```
Remove-VHDSnapshot [-PersistReferencePoint] [-VHDSnapshot] <VHDSnapshotInfo[]> [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Remove-VHDSnapshot` cmdlet removes a virtual hard disk (VHD) checkpoint from a VHD set file.

Checkpoint replaces the previous term, snapshot.

## EXAMPLES

### Example 1: Remove a checkpoint

```powershell
Remove-VHDSnapshot -Path "Data01.vhds" -SnapshotId 6c87351a-a39a-4581-b231-6d693b26485d
```

This command removes the checkpoint that has the specified ID from the VHD set file named
`Data01.vhds`.

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

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967)
or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet. The default is the
current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Specifies one or more Hyper-V hosts that run this cmdlet. NetBIOS names, IP addresses, and fully
qualified domain names are allowable. The default is the local computer. Use `localhost` or a dot
(`.`) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
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

Specifies one or more user accounts that have permission to perform this action. The default is the
current user.

```yaml
Type: PSCredential[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Specifies an array of paths of VHD set files. This cmdlet removes a checkpoint from the files that
this parameter specifies. If you specify a file name or relative path, the cmdlet determines the
full path relative to the current working folder.

```yaml
Type: String[]
Parameter Sets: Path
Aliases: FullName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PersistReferencePoint

Indicates that this cmdlet persists an RCT-only reference point after it deletes the checkpoint.

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

### -SnapshotId

Specifies an array of unique IDs of VHD checkpoint that this cmdlet removes from the VHD set file.

```yaml
Type: Guid[]
Parameter Sets: Path
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VHDSnapshot

Specifies an array of VHD checkpoints that this cmdlet removes from a VHD set file.

```yaml
Type: VHDSnapshotInfo[]
Parameter Sets: VHDSnapshot
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### Microsoft.Vhd.PowerShell.VHDSnapshotInfo[]

## OUTPUTS

### Microsoft.Vhd.PowerShell.VHDSnapshotInfo[]

## NOTES

## RELATED LINKS

[Get-VHDSnapshot](get-vhdsnapshot.md)
