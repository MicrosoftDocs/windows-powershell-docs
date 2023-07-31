---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 06/21/2023
online version: https://learn.microsoft.com/powershell/module/hyper-v/dismount-vhd?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Dismount-VHD
---

# Dismount-VHD

## SYNOPSIS
Dismounts a virtual hard disk.

## SYNTAX

### Path (Default)

```
Dismount-VHD [-Path] <String[]> [-SnapshotId <Guid>] [-PassThru]
 [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Disk

```
Dismount-VHD [-DiskNumber] <UInt32> [-PassThru] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The `Dismount-VHD` cmdlet dismounts a virtual hard disk.

## EXAMPLES

### Example 1

```powershell
Dismount-VHD -Path C:\test\testvhdx.vhdx
```

Dismounts an attached virtual hard disk where the path to the virtual hard disk file path is
`C:\test\testvhdx.vhdx`.

### Example 2

```powershell
Dismount-VHD -DiskNumber 6
```

Dismounts the attached virtual hard disk image with disk number 6.

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

Specifies one or more Hyper-V hosts on which a virtual hard disk is to be dismounted. NetBIOS names,
IP addresses, and fully qualified domain names are allowable. The default is the local computer. Use
`localhost` or a dot (`.`) to specify the local computer explicitly.

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

### -DiskNumber

Specifies the disk number of the virtual hard disk to be dismounted.

```yaml
Type: UInt32
Parameter Sets: Disk
Aliases: Number

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Specifies that an object is to be passed through to the pipeline representing the virtual hard disk
to be dismounted.

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

Specifies one or more virtual hard disk files for which the corresponding virtual hard disks are to
be dismounted.

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

### -SnapshotId

Specifies the unique ID of a VHD set snapshot.

```yaml
Type: Guid
Parameter Sets: Path
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

### System.UInt32

### System.String[]

### System.Nullable`1[[System.Guid, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]

## OUTPUTS

### Microsoft.Vhd.PowerShell.VirtualHardDisk

## NOTES

## RELATED LINKS

[Convert-VHD](convert-vhd.md)

[Get-VHD](get-vhd.md)

[Merge-VHD](merge-vhd.md)

[Mount-VHD](mount-vhd.md)

[New-VHD](new-vhd.md)

[Optimize-VHD](optimize-vhd.md)

[Resize-VHD](resize-vhd.md)

[Set-VHD](set-vhd.md)

[Test-VHD](test-vhd.md)
