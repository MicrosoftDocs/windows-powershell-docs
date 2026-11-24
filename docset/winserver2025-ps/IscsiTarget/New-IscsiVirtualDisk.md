---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
Module Name: IscsiTarget
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iscsitarget/new-iscsivirtualdisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-IscsiVirtualDisk
---

# New-IscsiVirtualDisk

## SYNOPSIS
Creates an iSCSI virtual disk with the specified file path and size.

## SYNTAX

### Dynamic (Default)
```
New-IscsiVirtualDisk [-Description <String>] [-Path] <String> [-SizeBytes] <UInt64>
 [-LogicalSectorSizeBytes <UInt32>] [-PhysicalSectorSizeBytes <UInt32>] [-BlockSizeBytes <UInt32>]
 [-ComputerName <String>] [-Credential <PSCredential>] [<CommonParameters>]
```

### Differencing
```
New-IscsiVirtualDisk [-Description <String>] -ParentPath <String> [-Path] <String> [[-SizeBytes] <UInt64>]
 [-PhysicalSectorSizeBytes <UInt32>] [-BlockSizeBytes <UInt32>] [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### Fixed
```
New-IscsiVirtualDisk [-Description <String>] [-Path] <String> [-SizeBytes] <UInt64> [-DoNotClearData]
 [-UseFixed] [-LogicalSectorSizeBytes <UInt32>] [-PhysicalSectorSizeBytes <UInt32>] [-BlockSizeBytes <UInt32>]
 [-ComputerName <String>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **New-IscsiVirtualDisk** cmdlet creates an iSCSI Virtual Hard Disk (VHDX) object that has the specified file path and size.
After the iSCSI VHDX object has been created, the virtual disk can be assigned to an iSCSI target.
Once a virtual disk has been assigned to a target, and an initiator connects to that target, the iSCSI initiator can then access the virtual disk after the initiator connects to the target.

If the virtual hard disk file path does not exist, a new VHDX file is created.

If the VHDX file path exists, the server returns an error.
Use the **Import-IscsiVirtualDisk** cmdlet to import existing virtual hard disks.

If the cmdlet displays an error while it creates a virtual disk, check the following conditions:

- An absolute file path must be specified for the *Path* and *ParentPath* parameters.

- The virtual disk file name must have a .vhdx file name extension.
- The VHDX file cannot be a network file, or be in a compressed, sparse, or transacted folder.

## EXAMPLES

### Example 1: Create a fixed VHDX
```
PS C:\> New-IscsiVirtualDisk -UseFixed -Path "E:\temp\test.vhdx" -Size 10GB
```

This example creates a fixed VHDX that is 10GB in size.

### Example 2: Create a differencing VHDX
```
PS C:\> New-IscsiVirtualDisk -ParentPath "E:\temp\test.vhdx" -Path "E:\temp\child\diff.vhdx"
```

This example creates a differencing VHDX, with the parent path E:\temp\test.vhdx and the differencing VHDX path is E:\temp\child\diff.vhdx.

### Example 3: Create a dynamic VHDX on a remote computer
```
PS C:\> New-IscsiVirtualDisk -Path "E:\temp\test.vhdx" -Size 10GB -ComputerName "iscsisvr"
```

This example creates a dynamic VHDX with the size 10GB at E:\temp\test.vhdx on the computer named iscsisvr.

### Example 4: Create a VHDX
```
PS C:\> New-IscsiVirtualDisk -Path "ramdisk:test.vhdx" -Size 20MB
```

This example creates a VHDX with the size 20MB.
This VHDX is not saved.
The VHDX is lost if the wintarget service is restarted or the system is restarted.

## PARAMETERS

### -BlockSizeBytes
Specifies the block size, in bytes, for the VHDX.
For fixed VHDX, if the value of the *SizeBytes* parameter is less than 32 MB, the default size if 2 MB.
Otherwise, the default value is 32 MB.
For dynamic VHDX, the default size is 2 MB.
For differencing VHDX, the default size is the parent *BlockSize*.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the computer name, or IP address, of the remote computer, if this cmdlet is run on a remote computer.

Specifies the cluster resource group network name, or cluster node name, if this cmdlet is run on a cluster configuration.

If you do not specify a value for this parameter, the cmdlet uses the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential
Specifies the credentials when connecting to a remote computer.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description
Specifies the description for the iSCSI virtual disk.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DoNotClearData
Indicates that the cmdlet does not clear the fixed VHDX.
Because failing to clear data can reveal pre-existing data, we do not recommend this option.

```yaml
Type: SwitchParameter
Parameter Sets: Fixed
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogicalSectorSizeBytes
Specifies the logical sector size, in bytes, for the VHDX.
The acceptable values for this parameter are: 512 and 4096.
The default value is 512.

```yaml
Type: UInt32
Parameter Sets: Dynamic, Fixed
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParentPath
Specifies the parent virtual disk path if the VHDX is a differencing disk.

```yaml
Type: String
Parameter Sets: Differencing
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the path of the VHDX file that is associated with the iSCSI virtual disk.
If the VHDX file path does not exist, a new VHDX file is created.
If the virtual hard disk file path exists, the server returns an error.
Use the **Import-IscsiVirtualDisk** cmdlet to import existing virtual hard drives.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DevicePath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PhysicalSectorSizeBytes
Specifies the physical sector size, in bytes, for the VHDX.
The acceptable values for this parameter are: 512 and 4096.
The default value is 4096.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SizeBytes
Specifies the size, in bytes, of the iSCSI virtual disk.

```yaml
Type: UInt64
Parameter Sets: Dynamic, Fixed
Aliases: Size

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: UInt64
Parameter Sets: Differencing
Aliases: Size

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseFixed
Indicates that the cmdlet creates a fixed VHDX.

```yaml
Type: SwitchParameter
Parameter Sets: Fixed
Aliases: Fixed

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Iscsi.Target.Commands.IscsiVirtualDisk

## NOTES

## RELATED LINKS

[Checkpoint-IscsiVirtualDisk](./Checkpoint-IscsiVirtualDisk.md)

[Convert-IscsiVirtualDisk](./Convert-IscsiVirtualDisk.md)

[Get-IscsiVirtualDisk](./Get-IscsiVirtualDisk.md)

[Import-IscsiVirtualDisk](./Import-IscsiVirtualDisk.md)

[Remove-IscsiVirtualDisk](./Remove-IscsiVirtualDisk.md)

[Restore-IscsiVirtualDisk](./Restore-IscsiVirtualDisk.md)

[Set-IscsiVirtualDisk](./Set-IscsiVirtualDisk.md)

