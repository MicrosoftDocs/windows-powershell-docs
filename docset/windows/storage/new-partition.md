---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Disk.cdxml-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: New-Partition
ms.reviewer:
ms.assetid: FD9EAA13-FD1A-4C95-A03E-842DBD1604BE
---

# New-Partition

## SYNOPSIS
Creates a new partition on an existing Disk object.

## SYNTAX

### ByNumber (Default)
```
New-Partition [-DiskNumber] <UInt32[]> [-Size <UInt64>] [-UseMaximumSize] [-Offset <UInt64>]
 [-Alignment <UInt32>] [-AssignDriveLetter] [-MbrType <MbrType>] [-GptType <String>]
 [-IsHidden] [-IsActive] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
New-Partition -DiskId <String[]> [-Size <UInt64>] [-UseMaximumSize] [-Offset <UInt64>] [-Alignment <UInt32>]
 [-DriveLetter <Char>] [-MbrType <MbrType>] [-GptType <String>] [-IsHidden] [-IsActive]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByPath
```
New-Partition -DiskPath <String[]> [-Size <UInt64>] [-UseMaximumSize] [-Offset <UInt64>] [-Alignment <UInt32>]
 [-DriveLetter <Char>] [-MbrType <MbrType>] [-GptType <String>] [-IsHidden] [-IsActive]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### InputObject (cdxml)
```
New-Partition -InputObject <CimInstance[]> [-Size <UInt64>] [-UseMaximumSize] [-Offset <UInt64>]
 [-Alignment <UInt32>] [-AssignDriveLetter] [-MbrType <MbrType>] [-GptType <String>]
 [-IsHidden] [-IsActive] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **New-Partition** cmdlet creates a partition on a specified Disk object.
Note: This cmdlet does not support creating dynamic volumes.

## EXAMPLES

### Example 1: Create a new partition on disk 1
```
PS C:\> New-Partition -DiskNumber 1 -UseMaximumSize -AssignDriveLetter
```

This example creates a new partition on disk 1, using the maximum available space, and automatically assigning a drive letter.

### Example 2: Get all RAW disks, initialize the disks, partition, and format them
```
This line gets all disk objects and then pipes the objects to the next command.
PS C:\>Get-Disk |

This line selects only objects where the PartitionStyle property value equals "RAW", and then pipes the objects to the next command.
PS C:\>Where-Object PartitionStyle -Eq "RAW" |

This line initializes all Disk objects in the pipeline and then pipes the objects to the next cmdlet.
PS C:\>Initialize-Disk -PassThru |

This line creates a maximum sized partition on each initialized Disk object, assigns a drive letter to the partitions, and then pipes the objects to the next cmdlet.
PS C:\>New-Partition -AssignDriveLetter -UseMaximumSize |

This line formats all newly partitioned disks.
PS C:\>Format-Volume
```

This example uses five cmdlets and the pipeline to get all disks, filter them for only RAW, unpartitioned disks, initialize the disks, partition the disks, and then format them.

## PARAMETERS

### -Alignment
Specifies the alignment boundary in bytes.

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

### -AssignDriveLetter
Assigns a drive letter to the new partition.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -DiskId
Specifies the ID of the disk on which to create the partition.

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskNumber
Specifies an array of disk numbers.

```yaml
Type: UInt32[]
Parameter Sets: ByNumber
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskPath
Specifies the path of the disk on which to create the partition.

```yaml
Type: String[]
Parameter Sets: ByPath
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DriveLetter
Specifies the specific drive letter to assign to the new partition.

```yaml
Type: Char
Parameter Sets: (All)
Aliases: NewDriveLetter

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GptType
Specifies the type of GPT partition to create (by GUID). 
The format should be 32 digits separated by hyphens, enclosed in braces:
{00000000-0000-0000-0000-000000000000}
By default, the **New-Partition** cmdlet creates a basic GPT data partition.

The GUIDs of valid types are: 
                         
 -- System Partition {c12a7328-f81f-11d2-ba4b-00a0c93ec93b}
                         
 -- Microsoft Reserved {e3c9e316-0b5c-4db8-817d-f92df00215ae}
                         
 -- Basic data {ebd0a0a2-b9e5-4433-87c0-68b6b72699c7}
                         
 -- Microsoft Recovery {de94bba4-06d1-4d40-a16a-bfd50179d6ac}

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

### -IsActive
Specifies that the object is marked active.

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

### -IsHidden
Creates a hidden partition.

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

### -MbrType
Specifies the type of MBR partition to create.
Valid types are: Extended, FAT12, FAT16, FAT32, Huge, and IFS.

```yaml
Type: MbrType
Parameter Sets: (All)
Aliases: 
Accepted values: FAT12, FAT16, Extended, Huge, IFS, FAT32

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Offset
Specifies the starting offset, in bytes.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Size
Specifies the size of the partition to create.
If not specified, then the units will default to **Bytes**.
The acceptable value for this parameter is a positive number followed by the one of the following unit values: **Bytes**, **KB**, **MB**, **GB**, or **TB**.

```yaml
Type: UInt64
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

### -UseMaximumSize
Creates the largest possible partition on the specified disk.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Disk
You can pipe a Disk object to the **InputObject** parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Partition
This cmdlet outputs an object that represents the newly created partition.

## NOTES

You can use either -AssignDriveLetter parameter or -DriveLetter parameter, but not both at the same time, while creating a new partition.

## RELATED LINKS

[Select-Object](http://go.microsoft.com/fwlink/p/?LinkId=113387)

[Add-PartitionAccessPath](./Add-PartitionAccessPath.md)

[Get-Partition](./Get-Partition.md)

[Set-Partition](./Set-Partition.md)

[Initialize-Disk](./Initialize-Disk.md)

[Format-Volume](./Format-Volume.md)

