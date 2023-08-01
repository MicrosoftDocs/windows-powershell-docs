---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 06/21/2023
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vhdsnapshot?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VHDSnapshot
---

# Get-VHDSnapshot

## SYNOPSIS
Gets information about a checkpoint in a VHD set.

## SYNTAX

```
Get-VHDSnapshot [-Path] <String[]> [-GetParentPaths] [-SnapshotId <Guid[]>]
 [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [<CommonParameters>]
```

## DESCRIPTION

The `Get-VHDSnapshot` cmdlet gets information about a checkpoint in a virtual hard disk (VHD) set
file.

Checkpoint replaces the previous term, snapshot.

## EXAMPLES

### Example 1: Get information about a checkpoint

```powershell
Get-VHDSnapshot -Path "Data01.vhds" -SnapshotId 6c87351a-a39a-4581-b231-6d693b26485d
```

This command gets information about the checkpoint that has the specified ID from the VHD set file
named `Data01.vhds` in the current working folder.

## PARAMETERS

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

Specifies one or more Hyper-V hosts that run this command. NetBIOS names, IP addresses, and fully
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

### -GetParentPaths

Gets the paths of all files on which this VHD checkpoint depends.

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

### -Path

Specifies an array of paths of VHD set files from which this cmdlet gets checkpoints. If you specify
a file name or relative path, the cmdlet determines the full path relative to the current working
folder.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: FullName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SnapshotId

Specifies an array of unique IDs of VHD checkpoints that this cmdlet gets from a VHD set file.

```yaml
Type: Guid[]
Parameter Sets: (All)
Aliases:

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

## OUTPUTS

### Microsoft.Vhd.PowerShell.VHDSnapshotInfo

This cmdlet returns a **VHDSnapshotInfo** object.

## NOTES

## RELATED LINKS

[Remove-VHDSnapshot](remove-vhdsnapshot.md)
