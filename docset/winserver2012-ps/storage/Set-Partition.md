---
author: Kateyanne
external help file: Storage2_Cmdlets.xml
manager: dansimp
Module Name: Storage
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/storage/set-partition?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-Partition

## SYNOPSIS
Sets attributes of a partition, such as active, read-only, and offline states.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-Partition [-DiskNumber] <UInt32> [-PartitionNumber] <UInt32> [-AsJob] [-CimSession <CimSession[]>]
 [-IsActive <Boolean>] [-IsHidden <Boolean>] [-IsReadOnly <Boolean>] [-NoDefaultDriveLetter <Boolean>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Set-Partition [-AsJob] [-CimSession <CimSession[]>] [-NewDriveLetter <Char>] [-ThrottleLimit <Int32>]
 -DiskId <String> -Offset <UInt64>
```

### UNNAMED_PARAMETER_SET_3
```
Set-Partition [-AsJob] [-CimSession <CimSession[]>] [-IsActive <Boolean>] [-IsHidden <Boolean>]
 [-IsReadOnly <Boolean>] [-NoDefaultDriveLetter <Boolean>] [-ThrottleLimit <Int32>] -DriveLetter <Char>
```

### UNNAMED_PARAMETER_SET_4
```
Set-Partition [-AsJob] [-CimSession <CimSession[]>] [-IsActive <Boolean>] [-IsHidden <Boolean>]
 [-IsReadOnly <Boolean>] [-NoDefaultDriveLetter <Boolean>] [-ThrottleLimit <Int32>] -DiskId <String>
 -Offset <UInt64>
```

### UNNAMED_PARAMETER_SET_5
```
Set-Partition [-AsJob] [-CimSession <CimSession[]>] [-NewDriveLetter <Char>] [-ThrottleLimit <Int32>]
 -DriveLetter <Char>
```

### UNNAMED_PARAMETER_SET_6
```
Set-Partition [-DiskNumber] <UInt32> [-PartitionNumber] <UInt32> [-AsJob] [-CimSession <CimSession[]>]
 [-IsOffline <Boolean>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_7
```
Set-Partition [-AsJob] [-CimSession <CimSession[]>] [-IsOffline <Boolean>] [-ThrottleLimit <Int32>]
 -DriveLetter <Char>
```

### UNNAMED_PARAMETER_SET_8
```
Set-Partition [-AsJob] [-CimSession <CimSession[]>] [-IsOffline <Boolean>] [-ThrottleLimit <Int32>]
 -DiskId <String> -Offset <UInt64>
```

### UNNAMED_PARAMETER_SET_9
```
Set-Partition [-AsJob] [-CimSession <CimSession[]>] [-IsOffline <Boolean>] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]>
```

### UNNAMED_PARAMETER_SET_10
```
Set-Partition [-AsJob] [-CimSession <CimSession[]>] [-NewDriveLetter <Char>] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]>
```

### UNNAMED_PARAMETER_SET_11
```
Set-Partition [-AsJob] [-CimSession <CimSession[]>] [-IsActive <Boolean>] [-IsHidden <Boolean>]
 [-IsReadOnly <Boolean>] [-NoDefaultDriveLetter <Boolean>] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]>
```

### UNNAMED_PARAMETER_SET_12
```
Set-Partition [-DiskNumber] <UInt32> [-PartitionNumber] <UInt32> [-AsJob] [-CimSession <CimSession[]>]
 [-NewDriveLetter <Char>] [-ThrottleLimit <Int32>]
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

### -DiskId
Specifies the disk ID of the partition to modify.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_8
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskNumber
Specifies the disk number of the partition to modify.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_6, UNNAMED_PARAMETER_SET_12
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DriveLetter
Specifies the drive letter of the partition to modify.

```yaml
Type: Char
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_7
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the Partition object to modify.
Enter a Partition CIM object.
The Partition object is exposed by the Get-Partition cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_9, UNNAMED_PARAMETER_SET_10, UNNAMED_PARAMETER_SET_11
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_11
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_11
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
Parameter Sets: UNNAMED_PARAMETER_SET_6, UNNAMED_PARAMETER_SET_7, UNNAMED_PARAMETER_SET_8, UNNAMED_PARAMETER_SET_9
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_11
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
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_10, UNNAMED_PARAMETER_SET_12
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_11
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
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_8
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_6, UNNAMED_PARAMETER_SET_12
Aliases: Number

Required: True
Position: 2
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

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Partition
You can pipe a Partition object to the InputObject parameter to specify the partition you want to modify by Partition object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-Partition](./Get-Partition.md)

[New-Partition](./New-Partition.md)

