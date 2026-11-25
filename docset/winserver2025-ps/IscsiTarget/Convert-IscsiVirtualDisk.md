---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
Module Name: IscsiTarget
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iscsitarget/convert-iscsivirtualdisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-IscsiVirtualDisk
---

# Convert-IscsiVirtualDisk

## SYNOPSIS
Converts an iSCSI virtual disk to a 4K sector aligned advanced virtual disk 1.0 format.

## SYNTAX

```
Convert-IscsiVirtualDisk [-Path] <String> [-DestinationPath] <String> [<CommonParameters>]
```

## DESCRIPTION
Note: This cmdlet is deprecated and might be removed in a future release.
We recommend that you do not use this cmdlet.

The **Convert-IscsiVirtualDisk** cmdlet converts an iSCSI virtual disk to a 4K sector aligned advanced virtual disk 1.0 format.
If an attempt is made to load a VHD created by the iSCSI Target 3.3, the VHD must be converted by running this cmdlet.
This cmdlet performs copy and conversion at the same time.
A remote file share or local path for both source and destination path can be specified.

Note: Use this cmdlet if iSCSI Target 3.3 differencing virtual disks are migrated to Windows Server 2012 R2 differencing virtual disks.

## EXAMPLES

### Example 1: Convert a VHD
```
PS C:\> Convert-IscsiVirtualDisk -Path "\\zamfirsvr\VHDs\test.vhdx" -DestinationPath "\\win8svr\VHDs\test.vhdx"
```

This example copies and converts the VHD named test.vhdx from \\\\zamfirsvr\VHDs\ to \\\\win8svr\VHDs.
The VHD named test.vhdx can be loaded after the conversion.

## PARAMETERS

### -DestinationPath
Specifies the destination path of the iSCSI virtual disk path of which to be copied and converted.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path of the virtual hard disk (VHD) file that is associated with the iSCSI virtual disk.
Filter the iSCSI Virtual Disk object by using this parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DevicePath

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Checkpoint-IscsiVirtualDisk](./Checkpoint-IscsiVirtualDisk.md)

[Get-IscsiVirtualDisk](./Get-IscsiVirtualDisk.md)

[Import-IscsiVirtualDisk](./Import-IscsiVirtualDisk.md)

[New-IscsiVirtualDisk](./New-IscsiVirtualDisk.md)

[Remove-IscsiVirtualDisk](./Remove-IscsiVirtualDisk.md)

[Restore-IscsiVirtualDisk](./Restore-IscsiVirtualDisk.md)

[Set-IscsiVirtualDisk](./Set-IscsiVirtualDisk.md)

