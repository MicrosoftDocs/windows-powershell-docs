---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: ms.date: 06/21/2023
online version: https://learn.microsoft.com/powershell/module/hyper-v/mount-vhd?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Mount-VHD
---

# Mount-VHD

## SYNOPSIS
Mounts one or more virtual hard disks.

## SYNTAX

```
Mount-VHD [-Path] <String[]> [-NoDriveLetter] [-ReadOnly] [-SnapshotId <Guid>] [-PassThru]
 [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Mount-VHD` cmdlet mounts one or more virtual hard disks.

## EXAMPLES

### Example 1

```powershell
Mount-VHD -Path C:\test\testvhdx.vhdx
```

Mounts a virtual hard disk where the path to the virtual hard disk file is C:\test\testvhdx.vhdx.

### Example 2

```powershell
Mount-VHD -Path C:\test\testvhdx.vhdx -ReadOnly
```

Mounts a virtual hard disk in read-only mode where the path to the virtual hard disk file is
C:\test\testvhdx.vhdx.

### Example 3

```powershell
Mount-VHD -Path C:\test\testvhdx -PassThru | Get-Disk | Get-Partition | Get-Volume
```

Attaches a virtual hard disk to the system where the path to the virtual hard disk file is
C:\test\testvhdx.vhdx, and gets the volumes associated with it.

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

Specifies one or more Hyper-V hosts on which a virtual hard disk is to be mounted. NetBIOS names, IP
addresses, and fully qualified domain names are allowable. The default is the local computer. Use
localhost or a dot (.) to specify the local computer explicitly.

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

### -NoDriveLetter

Specifies that the virtual hard disk is to be mounted without assigning drive letters to the volumes
contained within the virtual hard disk.

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

### -PassThru

Specifies that an object is to be passed through to the pipeline representing the virtual hard disk
to be mounted.

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

Specifies the path to the virtual hard disk file for the virtual hard disk to be mounted. If a
filename or relative path is specified, the virtual hard disk path is calculated relative to the
current working directory.

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

### -ReadOnly

Specifies that the virtual hard disk is to be mounted in read-only mode.

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

Specifies the unique ID of a VHD set.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System.Nullable`1[[System.Guid, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]

## OUTPUTS

### Microsoft.Vhd.PowerShell.VirtualHardDisk

## NOTES

## RELATED LINKS

- [Convert-VHD](convert-vhd.md)
- [Dismount-VHD](dismount-vhd.md)
- [Get-VHD](get-vhd.md)
- [Merge-VHD](merge-vhd.md)
- [New-VHD](new-vhd.md)
- [Optimize-VHD](optimize-vhd.md)
- [Resize-VHD](resize-vhd.md)
- [Set-VHD](set-vhd.md)
- [Test-VHD](test-vhd.md)
