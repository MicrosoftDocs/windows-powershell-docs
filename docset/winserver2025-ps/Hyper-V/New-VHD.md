---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/new-vhd?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-VHD
---

# New-VHD

## SYNOPSIS
Creates one or more new virtual hard disks.

## SYNTAX

### DynamicWithoutSource (Default)
```
New-VHD [-Path] <String[]> [-SizeBytes] <UInt64> [-Dynamic] [-BlockSizeBytes <UInt32>]
 [-LogicalSectorSizeBytes <UInt32>] [-PhysicalSectorSizeBytes <UInt32>] [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Differencing
```
New-VHD [-Path] <String[]> [-ParentPath] <String> [[-SizeBytes] <UInt64>] [-Differencing]
 [-BlockSizeBytes <UInt32>] [-PhysicalSectorSizeBytes <UInt32>] [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FixedWithoutSource
```
New-VHD [-Path] <String[]> [-SizeBytes] <UInt64> [-Fixed] [-BlockSizeBytes <UInt32>]
 [-LogicalSectorSizeBytes <UInt32>] [-PhysicalSectorSizeBytes <UInt32>] [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FixedWithSource
```
New-VHD [-Path] <String[]> -SourceDisk <UInt32> [-Fixed] [-BlockSizeBytes <UInt32>] [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DynamicWithSource
```
New-VHD [-Path] <String[]> -SourceDisk <UInt32> [-Dynamic] [-BlockSizeBytes <UInt32>] [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-VHD** cmdlet creates one or more new virtual hard disks in either VHD format or the newer VHDX format.
The file name extension you specify determines the format.

## EXAMPLES

### Example 1
```
PS C:\> New-VHD -Path c:\Base.vhdx -SizeBytes 10GB
```

This example creates a dynamic virtual hard disk in VHDX format that is 10 GB in size.
The file name extension determines the format and the default type of dynamic is used because no type is specified.

### Example 2
```
PS C:\> New-VHD -ParentPath c:\Base.vhdx -Path c:\Diff.vhdx -Differencing
```

This example creates a VHDX-format differencing virtual hard disk with a parent path of c:\Base.vhdx.

### Example 3
```
PS C:\> New-VHD -Path C:\fixed.vhd -Fixed -SourceDisk 2 -SizeBytes 1TB
```

This example creates a 1 TB VHD-format fixed virtual hard disk at the specified path.
The data for the virtual hard disk is populated from the disk identified in the system by the number 2.
You can list the disks attached to the system and the number associated with each disk using the **Get-Disk** cmdlet.

### Example 4
```
PS C:\> New-VHD -Path c:\LargeSectorBlockSize.vhdx -BlockSizeBytes 128MB -LogicalSectorSize 4KB -SizeBytes 1TB
```

This example creates a new 1 TB VHDX-format dynamic virtual hard disk at the specified path with a block size of 128 MB and a logical sector size of 4 KB.

### Example 5
```
PS C:\> $vhdpath = "C:\VHDs\Test.vhdx"
PS C:\> $vhdsize = 127GB
PS C:\> New-VHD -Path $vhdpath -Dynamic -SizeBytes $vhdsize | Mount-VHD -Passthru |Initialize-Disk -Passthru |New-Partition -AssignDriveLetter -UseMaximumSize |Format-Volume -FileSystem NTFS -Confirm:$false -Force
```

This example creates a new 127GB VHD and then mounts, initializes, and formats it so the drive is ready to use.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

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
Specifies one or more Hyper-V hosts on which the virtual hard disk file(s) are to be created.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

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
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

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

### -Differencing
Specifies that a differencing virtual hard disk is to be created.

```yaml
Type: SwitchParameter
Parameter Sets: Differencing
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
Parameter Sets: DynamicWithoutSource
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: SwitchParameter
Parameter Sets: DynamicWithSource
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
Parameter Sets: FixedWithoutSource, FixedWithSource
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogicalSectorSizeBytes
Specifies the logical sector size, in bytes, of the virtual hard disk to be created.
Valid values are 512 and 4096.

```yaml
Type: UInt32
Parameter Sets: DynamicWithoutSource, FixedWithoutSource
Aliases:
Accepted values: 512, 4096

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParentPath
Specifies the path to the parent of the differencing disk to be created (this parameter may be specified only for the creation of a differencing disk).

```yaml
Type: String
Parameter Sets: Differencing
Aliases:

Required: True
Position: 1
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
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PhysicalSectorSizeBytes
Specifies the physical sector size, in bytes.
Valid values are 512 and 4096.

```yaml
Type: UInt32
Parameter Sets: DynamicWithoutSource, Differencing, FixedWithoutSource
Aliases:
Accepted values: 512, 4096

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
Parameter Sets: DynamicWithoutSource, FixedWithoutSource
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: UInt64
Parameter Sets: Differencing
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceDisk
Specifies the physical disk to be used as the source for the virtual hard disk to be created.

```yaml
Type: UInt32
Parameter Sets: FixedWithSource, DynamicWithSource
Aliases: Number

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

## OUTPUTS

### Microsoft.Vhd.PowerShell.VirtualHardDisk

## NOTES

## RELATED LINKS

