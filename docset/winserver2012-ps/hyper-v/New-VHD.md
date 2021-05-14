---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/new-vhd?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-VHD

## SYNOPSIS
Creates one or more new virtual hard disks.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-VHD [-Path] <String[]> [-SizeBytes] <UInt64> [-AsJob] [-BlockSizeBytes <UInt32>] [-ComputerName <String[]>]
 [-Dynamic] [-LogicalSectorSizeBytes <UInt32>] [-PhysicalSectorSizeBytes <UInt32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
New-VHD [-Path] <String[]> [-ParentPath] <String> [[-SizeBytes] <UInt64>] [-AsJob] [-BlockSizeBytes <UInt32>]
 [-ComputerName <String[]>] [-Differencing] [-PhysicalSectorSizeBytes <UInt32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
New-VHD [-Path] <String[]> [-AsJob] [-BlockSizeBytes <UInt32>] [-ComputerName <String[]>] [-Dynamic]
 -SourceDisk <UInt32> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
New-VHD [-Path] <String[]> [-AsJob] [-BlockSizeBytes <UInt32>] [-ComputerName <String[]>] [-Fixed]
 -SourceDisk <UInt32> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
New-VHD [-Path] <String[]> [-SizeBytes] <UInt64> [-AsJob] [-BlockSizeBytes <UInt32>] [-ComputerName <String[]>]
 [-LogicalSectorSizeBytes <UInt32>] [-PhysicalSectorSizeBytes <UInt32>] [-Fixed] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **New-VHD** cmdlet creates one or more new virtual hard disks in either VHD format or the newer VHDX format.
The file extension you specify determines the format.

## EXAMPLES

### Example 1
```
PS C:\>New-VHD -Path c:\Base.vhdx -SizeBytes 10GB
```

This example creates a dynamic virtual hard disk in VHDX format that is 10 GB in size.
The file extension determines the format and the default type of dynamic is used because no type is specified.

### Example 2
```
PS C:\>New-VHD -ParentPath c:\Base.vhdx -Path c:\Diff.vhdx -Differencing
```

This example creates a VHDX-format differencing virtual hard disk with a parent path of c:\Base.vhdx.

### Example 3
```
PS C:\>New-VHD -Path C:\fixed.vhd -Fixed -SourceDisk 2 -SizeBytes 1TB
```

This example creates a 1 TB VHD-format fixed virtual hard disk at the specified path.
The data for the virtual hard disk is populated from the disk identified in the system by the number 2.
You can list the disks attached to the system and the number associated with each disk using the Get-Disk cmdlet.

### Example 4
```
PS C:\>New-VHD -Path c:\LargeSectorBlockSize.vhdx -BlockSizeBytes 128MB -LogicalSectorSize 4KB -SizeBytes 1TB
```

This example creates a new 1 TB VHDX-format dynamic virtual hard disk at the specified path with a block size of 128 MB and a logical sector size of 4 KB.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.

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

### -BlockSizeBytes
Specifies the block size, in bytes, of the virtual hard disk to be created.

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
Specifies one or more Hyper-V hosts on which the virtual hard disk file(s) are to be created.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogicalSectorSizeBytes
Specifies the logical sector size, in bytes, of the virtual hard disk to be created.
Valid values are 512 and 4096.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: 512
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParentPath
Specifies the path to the parent of the differencing disk to be created (this parameter may be specified only for the creation of a differencing disk).

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Path to the new virtual hard disk file(s) that is being created as a result of a command.
If a filename or relative path is specified, the new virtual hard disk path is calculated relative to the current working directory.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -PhysicalSectorSizeBytes
Specifies the physical sector size, in bytes.
Valid values are 512 and 4096.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SizeBytes
The maximum size, in bytes, of the virtual hard disk to be created.

```yaml
Type: UInt64
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: UInt64
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceDisk
Specifies the physical disk to be used as the source for the virtual hard disk to be created.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: Number

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Differencing
Specifies that a differencing virtual hard disk is to be created.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Dynamic
Specifies that a dynamic virtual hard disk is to be created.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Fixed
Specifies that a fixed virtual hard disk is to be created.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: True
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

## OUTPUTS

### VHDObject[]

## NOTES

## RELATED LINKS



