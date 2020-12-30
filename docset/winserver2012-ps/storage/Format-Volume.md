---
external help file: Storage2_Cmdlets.xml
online version:
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 4E32B0ED-FAA5-4DED-A96C-AE4C5A49CF8D
manager: dansimp
---

# Format-Volume

## SYNOPSIS
Formats one or more existing volumes or a new volume on an existing partition.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Format-Volume [-DriveLetter] <Char[]> [-AllocationUnitSize <UInt32>] [-AsJob] [-CimSession <CimSession[]>]
 [-Compress] [-FileSystem <String>] [-Force] [-Full] [-NewFileSystemLabel <String>]
 [-SetIntegrityStreams <Boolean>] [-ShortFileNameSupport <Boolean>] [-ThrottleLimit <Int32>] [-UseLargeFRS]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Format-Volume [-AllocationUnitSize <UInt32>] [-AsJob] [-CimSession <CimSession[]>] [-Compress]
 [-FileSystem <String>] [-Force] [-Full] [-NewFileSystemLabel <String>] [-Partition <CimInstance>]
 [-SetIntegrityStreams <Boolean>] [-ShortFileNameSupport <Boolean>] [-ThrottleLimit <Int32>] [-UseLargeFRS]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Format-Volume [-AllocationUnitSize <UInt32>] [-AsJob] [-CimSession <CimSession[]>] [-Compress]
 [-FileSystem <String>] [-Force] [-Full] [-NewFileSystemLabel <String>] [-SetIntegrityStreams <Boolean>]
 [-ShortFileNameSupport <Boolean>] [-ThrottleLimit <Int32>] [-UseLargeFRS] -InputObject <CimInstance[]>
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Format-Volume [-AllocationUnitSize <UInt32>] [-AsJob] [-CimSession <CimSession[]>] [-Compress]
 [-FileSystem <String>] [-Force] [-Full] [-NewFileSystemLabel <String>] [-SetIntegrityStreams <Boolean>]
 [-ShortFileNameSupport <Boolean>] [-ThrottleLimit <Int32>] [-UseLargeFRS] -FileSystemLabel <String[]>
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Format-Volume [-AllocationUnitSize <UInt32>] [-AsJob] [-CimSession <CimSession[]>] [-Compress]
 [-FileSystem <String>] [-Force] [-Full] [-NewFileSystemLabel <String>] [-SetIntegrityStreams <Boolean>]
 [-ShortFileNameSupport <Boolean>] [-ThrottleLimit <Int32>] [-UseLargeFRS] -ObjectId <String[]> [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_6
```
Format-Volume [-AllocationUnitSize <UInt32>] [-AsJob] [-CimSession <CimSession[]>] [-Compress]
 [-FileSystem <String>] [-Force] [-Full] [-NewFileSystemLabel <String>] [-SetIntegrityStreams <Boolean>]
 [-ShortFileNameSupport <Boolean>] [-ThrottleLimit <Int32>] [-UseLargeFRS] -Path <String[]> [-Confirm]
 [-WhatIf]
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

### -DriveLetter
Specifies the drive letter of the volume to format.

```yaml
Type: Char[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases:

Required: True
Position: 1
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
Parameter Sets: UNNAMED_PARAMETER_SET_4
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
Parameter Sets: UNNAMED_PARAMETER_SET_3
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
Parameter Sets: UNNAMED_PARAMETER_SET_5
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_6
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Volume
You can pipe an MSFT_Volume object to the InputObject parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Partition
You can pipe an MSFT_Partition object to the Partition parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Volume
The Format-Volume cmdlet return an object representing the newly formatted volume.

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

