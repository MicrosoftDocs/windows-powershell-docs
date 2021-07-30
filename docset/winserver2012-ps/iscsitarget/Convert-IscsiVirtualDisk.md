---
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
Module Name: IscsiTarget
online version: https://docs.microsoft.com/powershell/module/iscsitarget/convert-iscsivirtualdisk?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Convert-IscsiVirtualDisk

## SYNOPSIS
Converts an iSCSI virtual disk to a Generation one Advanced Format-aligned (4K sector technology) virtual disk.

## SYNTAX

```
Convert-IscsiVirtualDisk [-Path] <String> [-DestinationPath] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Convert-IscsiVirtualDisk** cmdlet converts an iSCSI virtual disk to a Generation one Advanced Format-aligned (4K sector technology) virtual disk.
If an attempt is made to load a VHD created by the previous version of the iSCSI Target in Windows Server® 2012, then the VHD must be converted by running this cmdlet.
This cmdlet performs copy and conversion at the same time.
A remote file share or local path for both source and destination path can be specified.

Note: Use this cmdlet if iSCSI Target 3.3 differencing virtual disks are migrated to Windows Server 2012 differencing virtual disks.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Convert-IscsiVirtualDisk -Path \\zamfirsvr\VHDs\test.vhd -DestinationPath \\win8svr\VHDs\test.vhd
```

This example copies and converts the VHD namedtest.vhd from \\\\zamfirsvr\VHDs\ to \\\\win8svr\VHDs.
The VHD named test.vhd can be loaded after the conversion.

## PARAMETERS

### -DestinationPath
Specifies the destination path of the iSCSI virtual disk path to which to be copied and converted.

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

Filter the iSCSI Virtual Disk object using this parameter.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Checkpoint-IscsiVirtualDisk](./Checkpoint-IscsiVirtualDisk.md)

[Expand-IscsiVirtualDisk](./Expand-IscsiVirtualDisk.md)

[Get-IscsiVirtualDisk](./Get-IscsiVirtualDisk.md)

[Import-IscsiVirtualDisk](./Import-IscsiVirtualDisk.md)

[New-IscsiVirtualDisk](./New-IscsiVirtualDisk.md)

[Remove-IscsiVirtualDisk](./Remove-IscsiVirtualDisk.md)

[Restore-IscsiVirtualDisk](./Restore-IscsiVirtualDisk.md)

[Set-IscsiVirtualDisk](./Set-IscsiVirtualDisk.md)

