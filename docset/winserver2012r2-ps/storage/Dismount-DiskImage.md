---
external help file: DiskImage.cdxml-help.xml
Module Name: Storage
online version: 
schema: 2.0.0
title: Dismount-DiskImage
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: B38C053D-45B5-49F5-AFF9-0228ED638828
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Dismount-DiskImage

## SYNOPSIS
Dismounts a disk image (virtual hard disk or ISO) so that it can no longer be accessed as a disk.

## SYNTAX

### ByImagePath (Default)
```
Dismount-DiskImage [-ImagePath] <String[]> [-StorageType <StorageType>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByDevicePath
```
Dismount-DiskImage -DevicePath <String[]> [-StorageType <StorageType>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Dismount-DiskImage -InputObject <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Dismount-DiskImage** cmdlet dismounts a disk image (virtual hard disk or ISO) so that it can no longer be accessed as a disk.
This cmdlet requires either the full image path of the ISO or VHD file, or the device path.

To eject a VHD file, administrator privilege is required.
Administrator privilege is not needed to eject an ISO file on Windows® 8.
On Windows Server® 2012, only an administrator is allowed to mount or eject ISO file.

## EXAMPLES

### Example 1: Dismount a disk image by path
```
PS C:\>Dismount-DiskImage -ImagePath "E:\ISO-Files\My US Visit Fall 2010 Pictures.iso"
```

This example ejects an ISO named My US Visit Fall 2010 Pictures by specifying the image path at E:\ISO-Files.

### Example 2: Dismount a disk image by device path
```
PS C:\>Dismount-DiskImage -DevicePath \\.\CDROM1
```

This example ejects an ISO by specifying device path for cdrom1.
Refer to the Get-DiskImage cmdlet to learn how to find the device path of an ISO or VHD file.

## PARAMETERS

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

### -DevicePath
Specifies the device path of the ISO/VHD file.
You cannot use this parameter with the **ImagePath** parameter.

```yaml
Type: String[]
Parameter Sets: ByDevicePath
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ImagePath
Specifies the path of the ISO or VHD file.
You cannot use this parameter with the **DevicePath** parameter.

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
Accepts an object from the pipeline as input.
This object is a DiskImage CIM object that is exposed by Get-DiskImage cmdlet, which is different from the VirtualHardDisk object output by the New-VHD cmdlet in the Hyper-V module.

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

### -PassThru
Specifies that the cmdlet should output an object representing the dismounted disk image.
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
If the StorageType parameter is not specified or the Unknown type is provided, the storage type is determined by file extension.

```yaml
Type: StorageType
Parameter Sets: ByImagePath, ByDevicePath
Aliases: 
Accepted values: Unknown, ISO, VHD, VHDX

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_DiskImage
You can pipe a DiskImage object to the InputObject parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_DiskImage
If you specify the **Passthru** parameter, this cmdlet outputs an object that represents the disk image that you dismounted.

## NOTES

## RELATED LINKS

[Get-DiskImage](./Get-DiskImage.md)

[Mount-DiskImage](./Mount-DiskImage.md)

