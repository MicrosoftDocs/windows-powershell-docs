---
author: Kateyanne
description: 
external help file: Volume.cdxml-help.xml
manager: jasgro
Module Name: Storage
ms.author: v-kaunu
ms.date: 10/29/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/storage/format-volume?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Volume
---

# Format-Volume

## SYNOPSIS
Formats one or more existing volumes or a new volume on an existing partition.

## SYNTAX

### ByDriveLetter (Default)
```
Format-Volume [-DriveLetter] <Char[]> [-FileSystem <String>] [-NewFileSystemLabel <String>]
 [-AllocationUnitSize <UInt32>] [-Full] [-Force] [-Compress] [-ShortFileNameSupport <Boolean>]
 [-SetIntegrityStreams <Boolean>] [-UseLargeFRS] [-DisableHeatGathering] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ById
```
Format-Volume -ObjectId <String[]> [-FileSystem <String>] [-NewFileSystemLabel <String>]
 [-AllocationUnitSize <UInt32>] [-Full] [-Force] [-Compress] [-ShortFileNameSupport <Boolean>]
 [-SetIntegrityStreams <Boolean>] [-UseLargeFRS] [-DisableHeatGathering] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByPaths
```
Format-Volume -Path <String[]> [-FileSystem <String>] [-NewFileSystemLabel <String>]
 [-AllocationUnitSize <UInt32>] [-Full] [-Force] [-Compress] [-ShortFileNameSupport <Boolean>]
 [-SetIntegrityStreams <Boolean>] [-UseLargeFRS] [-DisableHeatGathering] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByLabel
```
Format-Volume -FileSystemLabel <String[]> [-FileSystem <String>] [-NewFileSystemLabel <String>]
 [-AllocationUnitSize <UInt32>] [-Full] [-Force] [-Compress] [-ShortFileNameSupport <Boolean>]
 [-SetIntegrityStreams <Boolean>] [-UseLargeFRS] [-DisableHeatGathering] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByPartition
```
Format-Volume [-Partition <CimInstance>] [-FileSystem <String>] [-NewFileSystemLabel <String>]
 [-AllocationUnitSize <UInt32>] [-Full] [-Force] [-Compress] [-ShortFileNameSupport <Boolean>]
 [-SetIntegrityStreams <Boolean>] [-UseLargeFRS] [-DisableHeatGathering] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Format-Volume -InputObject <CimInstance[]> [-FileSystem <String>] [-NewFileSystemLabel <String>]
 [-AllocationUnitSize <UInt32>] [-Full] [-Force] [-Compress] [-ShortFileNameSupport <Boolean>]
 [-SetIntegrityStreams <Boolean>] [-UseLargeFRS] [-DisableHeatGathering] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Format-Volume** cmdlet formats one or more existing volumes, or a new volume on an existing partition.
This cmdlet returns the object representing the volume that was just formatted, with all properties updated to reflect the format operation.

To create a new volume, use this cmdlet in conjunction with the Initialize-Disk and New-Partition cmdlets.

## EXAMPLES

### Example 1: Quick format
```
PS C:\>Format-Volume -DriveLetter D
```

This example performs a format of the D volume.

### Example 2: Full format using FAT32
```
PS C:\>Format-Volume -DriveLetter D -FileSystem FAT32 -Full -Force
```

This example performs a full format of the D volume using the FAT32 file system.

## PARAMETERS

### -AllocationUnitSize
Specifies the allocation unit size to use when formatting the volume.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: ClusterSize

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

### -Compress
Enables compression on all files and folders created on the specified NTFS volume.

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

### -DisableHeatGathering
Indicates that the cmdlet does not gather file activity on the specified tiered volume.
You can override file placement based on the desired storage tier.
This parameter is only valid for tiered volumes.

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

### -DriveLetter
Specifies the drive letter of the volume to format.

```yaml
Type: Char[]
Parameter Sets: ByDriveLetter
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FileSystem
Specifies the file system with which to format the volume.
The acceptable values for this parameter are:NTFS, ReFS, exFAT, FAT32, and FAT.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: FAT, FAT32, exFAT, NTFS, ReFS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileSystemLabel
Specifies the label to use for the volume.

```yaml
Type: String[]
Parameter Sets: ByLabel
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Specifies the override switch.

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

### -Full
Performs a full format.
A full format writes to every sector of the disk, takes much longer to perform than the default (quick) format, and is not recommended on storage that is thinly provisioned.

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

### -InputObject
Specifies one or more existing Volume objects to format.
Enter one or more Volume CIM objects, which is output by the Get-Volume cmdlet.

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

### -NewFileSystemLabel
Specifies a new label to use for the volume.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ObjectId
Specifies the ID of the volume to format.

```yaml
Type: String[]
Parameter Sets: ById
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Partition
Specifies the partition object on which to create the new volume.
Enter a Partition CIM object, which is exposed by the Get-Partition and New-Partition cmdlets.

```yaml
Type: CimInstance
Parameter Sets: ByPartition
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Path
Specifies the path of the volume to format.

```yaml
Type: String[]
Parameter Sets: ByPaths
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SetIntegrityStreams
Enables integrity streams on the volume to be formatted.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShortFileNameSupport
Specifies that support for short file names should be enabled on this volume.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -UseLargeFRS
Specifies that large File Record Segment (FRS) should be used.

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Volume
You can use the pipeline operator to pass an MSFT_Volume object to the InputObject parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Partition
You can use the pipeline operator to pass an MSFT_Partition object to the Partition parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Volume
This cmdlet returns an object that represents the newly formatted volume.

## NOTES

## RELATED LINKS

[Get-Disk](./Get-Disk.md)

[Initialize-Disk](./Initialize-Disk.md)

[New-Partition](./New-Partition.md)

[Get-Partition](./Get-Partition.md)

[Get-Volume](./Get-Volume.md)

[Optimize-Volume](./Optimize-Volume.md)

[Repair-Volume](./Repair-Volume.md)

[Set-Volume](./Set-Volume.md)

