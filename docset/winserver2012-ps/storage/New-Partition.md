---
external help file: Storage2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: FD9EAA13-FD1A-4C95-A03E-842DBD1604BE
---

# New-Partition

## SYNOPSIS
Creates a new partition on an existing Disk object.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-Partition [-DiskNumber] <UInt32[]> [-Alignment <UInt32>] [-AsJob] [-AssignDriveLetter]
 [-CimSession <CimSession[]>] [-DriveLetter <Char>] [-GptType <String>] [-IsActive] [-IsHidden]
 [-MbrType <MbrType>] [-Offset <UInt64>] [-Size <UInt64>] [-ThrottleLimit <Int32>] [-UseMaximumSize]
```

### UNNAMED_PARAMETER_SET_2
```
New-Partition [-Alignment <UInt32>] [-AsJob] [-AssignDriveLetter] [-CimSession <CimSession[]>]
 [-DriveLetter <Char>] [-GptType <String>] [-IsActive] [-IsHidden] [-MbrType <MbrType>] [-Offset <UInt64>]
 [-Size <UInt64>] [-ThrottleLimit <Int32>] [-UseMaximumSize] -DiskPath <String[]>
```

### UNNAMED_PARAMETER_SET_3
```
New-Partition [-Alignment <UInt32>] [-AsJob] [-AssignDriveLetter] [-CimSession <CimSession[]>]
 [-DriveLetter <Char>] [-GptType <String>] [-IsActive] [-IsHidden] [-MbrType <MbrType>] [-Offset <UInt64>]
 [-Size <UInt64>] [-ThrottleLimit <Int32>] [-UseMaximumSize] -DiskId <String[]>
```

### UNNAMED_PARAMETER_SET_4
```
New-Partition [-Alignment <UInt32>] [-AsJob] [-AssignDriveLetter] [-CimSession <CimSession[]>]
 [-DriveLetter <Char>] [-GptType <String>] [-IsActive] [-IsHidden] [-MbrType <MbrType>] [-Offset <UInt64>]
 [-Size <UInt64>] [-ThrottleLimit <Int32>] [-UseMaximumSize] -InputObject <CimInstance[]>
```

## DESCRIPTION
The **New-Partiton** cmdlet creates a partition on a specified Disk object.
Note: This cmdlet does not support creating dynamic volumes.

## EXAMPLES

### Example 1: Create a new partition on disk 1
```
PS C:\> New-Partiton -DiskNumber 1 -UseMaximumSize -AssignDriveLetter
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

### -DiskId
Specifies the ID of the disk on which to create the partition.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskNumber
Specifies the number of the disk.

```yaml
Type: UInt32[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskPath
Specifies the path of the disk on which to create the partition.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
By default, the **New-Partition** cmdlet creates a basic GPT data partition.

The GUIDs of valid types are: 
                         
 -- System Partition (c12a7328-f81f-11d2-ba4b-00a0c93ec93b) 
                         
 -- Microsoft Reserved (e3c9e316-0b5c-4db8-817d-f92df00215ae)
                         
 -- Basic data (ebd0a0a2-b9e5-4433-87c0-68b6b72699c7) 
                         
 -- Microsoft Recovery (de94bba4-06d1-4d40-a16a-bfd50179d6ac)

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
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_4
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

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Disk
You can pipe a Disk object to the **InputObject** parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Partition
This cmdlet outputs an object that represents the newly created partition.

## NOTES

## RELATED LINKS

[Select-Object](http://go.microsoft.com/fwlink/p/?LinkId=113387)

[Add-PartitionAccessPath](./Add-PartitionAccessPath.md)

[Get-Partition](./Get-Partition.md)

[Set-Partition](./Set-Partition.md)

[Initialize-Disk](./Initialize-Disk.md)

[Format-Volume](./Format-Volume.md)

