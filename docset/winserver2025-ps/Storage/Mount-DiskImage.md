---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DiskImage.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/mount-diskimage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Mount-DiskImage
---

# Mount-DiskImage

## SYNOPSIS
Mounts a previously created disk image (virtual hard disk or ISO), making it appear as a normal disk.

## SYNTAX

### ByImagePath (Default)
```
Mount-DiskImage [-ImagePath] <String[]> [-StorageType <StorageType>] [-Access <Access>] [-NoDriveLetter]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Mount-DiskImage -InputObject <CimInstance[]> [-Access <Access>] [-NoDriveLetter] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Mount-DiskImage** cmdlet mounts a previously created disk image (virtual hard disk or ISO), making it appear as a normal disk.
This cmdlet requires the full path of the VHD or ISO file.
If the file is already mounted, then the cmdlet will display the following error.

 -- `"The process cannot access the file because it is being used by another process."`

To mount a VHD file, administrator privileges is required.
Administrator privileges are not needed to mount an ISO file on Windows® 8.
On Windows Server® 2012, only an administrator is allowed to mount or eject an ISO file.

To create and mount a VHD on a computer running Hyper-V, use the New-VHD and Mount-VHD cmdlets in the Hyper-V module (which is included in Windows 8 and Windows Server 2012 but not enabled by default).
Alternatively, open Disk Management and then choose Create VHD from the Action menu.

## EXAMPLES

### Example 1: Mounting an ISO
```
PS C:\>Mount-DiskImage -ImagePath "E:\ISO-Files\My US Visit Fall 2010 Pictures.iso"
```

This example mounts an ISO by specifying the image path.

## PARAMETERS

### -Access
Mounts the VHD file in read-only or read-write mode.
If this parameter is not used or you specify the *Unknown* parameter value for the VHD file, the VHD file is mounted in read-write mode.

ISO files are mounted in read-only mode regardless of what parameter value you provide.

```yaml
Type: Access
Parameter Sets: (All)
Aliases:
Accepted values: Unknown, ReadWrite, ReadOnly

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Parameter Sets: (All)
Aliases: Session

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

### -ImagePath
Specifies the path of the VHD or ISO file.

```yaml
Type: String[]
Parameter Sets: ByImagePath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NoDriveLetter
Specifies that no drive letter should be assigned to the VHD or ISO file after mounting.

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
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -StorageType
Specifies the storage type of a file: ISO, VHD, VHDx, or Unknown.
If the *StorageType* parameter is not specified or the Unknown type is provided, then the storage type is determined by file extension.

```yaml
Type: StorageType
Parameter Sets: ByImagePath
Aliases:
Accepted values: Unknown, ISO, VHD, VHDX, VHDSet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_DiskImage
You can pipe a DiskImage object to the *InputObject* parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_DiskImage
If you specify the *Passthru* parameter, this cmdlet outputs an object that represents the disk image that you mounted.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Dismount-DiskImage](./Dismount-DiskImage.md)

[Get-DiskImage](./Get-DiskImage.md)

