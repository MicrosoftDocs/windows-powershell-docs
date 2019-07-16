---
external help file: Storage2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: E10B4E05-1D98-4EAA-A6BE-2D3F4A885746
manager: dansimp
---

# Mount-DiskImage

## SYNOPSIS
Mounts a previously created disk image (virtual hard disk or ISO), making it appear as a normal disk.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Mount-DiskImage [-ImagePath] <String[]> [-Access <Access>] [-AsJob] [-CimSession <CimSession[]>]
 [-NoDriveLetter] [-PassThru] [-StorageType <StorageType>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Mount-DiskImage [-Access <Access>] [-AsJob] [-CimSession <CimSession[]>] [-NoDriveLetter] [-PassThru]
 [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
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
If this parameter is not used or you specify the **Unknown** parameter value for the VHD file, the VHD file is mounted in read-write mode.

ISO files are mounted in read-only mode regardless of what parameter value you provide.

```yaml
Type: Access
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -ImagePath
Specifies the path of the VHD or ISO file.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Accepts an object from the pipeline as input.
This object is a DiskImage CIM object that is exposed by Get-DiskImage cmdlet, which is different from the VirtualHardDisk object output by the New-VHD cmdlet in the Hyper-V module.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
If the **StorageType** parameter is not specified or the Unknown type is provided, then the storage type is determined by file extension.

```yaml
Type: StorageType
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_DiskImage
You can pipe a DiskImage object to the InputObject parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_DiskImage
If you specify the **Passthru** parameter, this cmdlet outputs an object that represents the disk image that you mounted.

## NOTES

## RELATED LINKS

[Dismount-DiskImage](./Dismount-DiskImage.md)

[Get-DiskImage](./Get-DiskImage.md)

[New-VHD](00000000-0000-0000-0000-000000000000)

