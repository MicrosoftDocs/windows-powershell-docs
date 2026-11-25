---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageCmdlets.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/set-partition?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Partition
---

# Set-Partition

## SYNOPSIS
Sets attributes of a partition, such as active, read-only, and offline states.

## SYNTAX

### ByNumberAttributes (Default)
```
Set-Partition [-IsReadOnly <Boolean>] [-NoDefaultDriveLetter <Boolean>] [-IsActive <Boolean>]
 [-IsHidden <Boolean>] [-IsShadowCopy <Boolean>] [-IsDAX <Boolean>] [-MbrType <UInt16>] [-GptType <String>]
 [-DiskNumber] <UInt32> [-PartitionNumber] <UInt32> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByObjectAccessPath
```
Set-Partition -InputObject <CimInstance[]> [-NewDriveLetter <Char>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByObject
```
Set-Partition -InputObject <CimInstance[]> [-IsOffline <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByObjectAttributes
```
Set-Partition -InputObject <CimInstance[]> [-IsReadOnly <Boolean>] [-NoDefaultDriveLetter <Boolean>]
 [-IsActive <Boolean>] [-IsHidden <Boolean>] [-IsShadowCopy <Boolean>] [-IsDAX <Boolean>] [-MbrType <UInt16>]
 [-GptType <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByDriveLetterAttributes
```
Set-Partition [-IsReadOnly <Boolean>] [-NoDefaultDriveLetter <Boolean>] [-IsActive <Boolean>]
 [-IsHidden <Boolean>] [-IsShadowCopy <Boolean>] [-IsDAX <Boolean>] [-MbrType <UInt16>] [-GptType <String>]
 -DriveLetter <Char> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByIdAttributes
```
Set-Partition [-IsReadOnly <Boolean>] [-NoDefaultDriveLetter <Boolean>] [-IsActive <Boolean>]
 [-IsHidden <Boolean>] [-IsShadowCopy <Boolean>] [-IsDAX <Boolean>] [-MbrType <UInt16>] [-GptType <String>]
 -DiskId <String> -Offset <UInt64> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByIdAccessPath
```
Set-Partition -DiskId <String> -Offset <UInt64> [-NewDriveLetter <Char>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ById
```
Set-Partition -DiskId <String> -Offset <UInt64> [-IsOffline <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByDriveLetterAccessPath
```
Set-Partition -DriveLetter <Char> [-NewDriveLetter <Char>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByDriveLetter
```
Set-Partition -DriveLetter <Char> [-IsOffline <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByNumberAccessPath
```
Set-Partition [-DiskNumber] <UInt32> [-PartitionNumber] <UInt32> [-NewDriveLetter <Char>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByNumber
```
Set-Partition [-DiskNumber] <UInt32> [-PartitionNumber] <UInt32> [-IsOffline <Boolean>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-Partition** cmdlet sets the attributes of a partition, including active, read-only, hidden, offline, and the drive letter.

## EXAMPLES

### Example 1: Set the partition to read-only
```
PS C:\> Set-Partition -DriveLetter Y -IsReadOnly $True
```

This example makes partition Y read-only.

### Example 2: Set an MBR partition to active
```
PS C:\> Set-Partition -DriveLetter Y -IsActive $True
```

This example makes the MBR partition Y active.

### Example 3: Hide the partition
```
PS C:\> Set-Partition -DriveLetter Y -IsHidden $True
```

This example hides partition Y.

### Example 4: Take the partition offline
```
PS C:\> Set-Partition -DriveLetter Y -IsOffline $True
```

This example takes the partition and volume offline.

### Example 5: Change the drive letter
```
PS C:\> Set-Partition -DriveLetter Y -NewDriveLetter Z
```

This example changes the drive letter from Y to Z.

## PARAMETERS

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

### -DiskId
Specifies the disk ID of the partition to modify.

```yaml
Type: String
Parameter Sets: ByIdAttributes, ByIdAccessPath, ById
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskNumber
Specifies an array of disk numbers.
These represent the disks on which the partitions reside to modify.

```yaml
Type: UInt32
Parameter Sets: ByNumberAttributes, ByNumberAccessPath, ByNumber
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DriveLetter
Specifies the drive letter of the partition to modify.

```yaml
Type: Char
Parameter Sets: ByDriveLetterAttributes, ByDriveLetterAccessPath, ByDriveLetter
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GptType
Sets the type of a GPT partition to a specific GUID.

```yaml
Type: String
Parameter Sets: ByNumberAttributes, ByObjectAttributes, ByDriveLetterAttributes, ByIdAttributes
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
Parameter Sets: ByObjectAccessPath, ByObject, ByObjectAttributes
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IsActive
Specifies that the partition is marked as active and can be used to start the system.
This parameter is only relevant for MBR disks.

```yaml
Type: Boolean
Parameter Sets: ByNumberAttributes, ByObjectAttributes, ByDriveLetterAttributes, ByIdAttributes
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsDAX
Formats a volume as a DirectAccess (DAX) volume.

DAX provides applications with direct access and byte-addressability options via memory mapping on storage class memory (SCM) devices, such as NVDIMM-N.

If you do not specify the *IsDAX* parameter, the cmdlet defaults to a regular, non-DAX volume.

```yaml
Type: Boolean
Parameter Sets: ByNumberAttributes, ByObjectAttributes, ByDriveLetterAttributes, ByIdAttributes
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsHidden
Specifies that the partition is hidden.
As a result, the partition does not receive a drive letter, does not receive a volume GUID path, and does not host volume mount points.
This ensures that applications such as disk defragmenter do not access the partition.

```yaml
Type: Boolean
Parameter Sets: ByNumberAttributes, ByObjectAttributes, ByDriveLetterAttributes, ByIdAttributes
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsOffline
Takes the partition offline until explicitly brought back online, or until an access path is added to the partition.

```yaml
Type: Boolean
Parameter Sets: ByObject, ById, ByDriveLetter, ByNumber
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsReadOnly
Sets the partition to be read-only (`IsReadOnly $true`) or read-write (`IsReadOnly $false`).

```yaml
Type: Boolean
Parameter Sets: ByNumberAttributes, ByObjectAttributes, ByDriveLetterAttributes, ByIdAttributes
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsShadowCopy


```yaml
Type: Boolean
Parameter Sets: ByNumberAttributes, ByObjectAttributes, ByDriveLetterAttributes, ByIdAttributes
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MbrType
Sets the type of an MBR partition to a specific numeric ID.

```yaml
Type: UInt16
Parameter Sets: ByNumberAttributes, ByObjectAttributes, ByDriveLetterAttributes, ByIdAttributes
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewDriveLetter
Specifies the new drive letter for the partition.

```yaml
Type: Char
Parameter Sets: ByObjectAccessPath, ByIdAccessPath, ByDriveLetterAccessPath, ByNumberAccessPath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoDefaultDriveLetter
Specifies that the automatic assignment of a drive letter is disabled.
This is only honored for GPT disks.
This attribute is useful in storage area network (SAN) environments.

```yaml
Type: Boolean
Parameter Sets: ByNumberAttributes, ByObjectAttributes, ByDriveLetterAttributes, ByIdAttributes
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Offset
Specifies the partition's offset from the beginning of the disk, measured in bytes.

```yaml
Type: UInt64
Parameter Sets: ByIdAttributes, ByIdAccessPath, ById
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PartitionNumber
Specifies the number of the partition.

```yaml
Type: UInt32
Parameter Sets: ByNumberAttributes, ByNumberAccessPath, ByNumber
Aliases: Number

Required: True
Position: 1
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Partition
You can pipe a Partition object to the InputObject parameter to specify the partition you want to modify by Partition object.

## OUTPUTS

### None

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-Partition](./Get-Partition.md)

[New-Partition](./New-Partition.md)

