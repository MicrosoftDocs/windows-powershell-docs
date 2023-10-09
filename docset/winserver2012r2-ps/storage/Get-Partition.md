---
external help file: Partition.cdxml-help.xml
Module Name: Storage
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/storage/get-partition?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Partition
---

# Get-Partition

## SYNOPSIS
Returns a list of all partition objects visible on all disks, or optionally a filtered list using specified parameters.

## SYNTAX

### ByNumber (Default)
```
Get-Partition [[-DiskNumber] <UInt32[]>] [[-PartitionNumber] <UInt32[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ById
```
Get-Partition [-DiskId <String[]>] [-Offset <UInt64[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByDriveLetter
```
Get-Partition [-DriveLetter <Char[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByDisk
```
Get-Partition [-Disk <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByVolume
```
Get-Partition [-Volume <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-Partition** cmdlet returns one or more Partition objects depending on the specified criteria.
This cmdlet will return a Volume object or a set of Volume objects given parameters to be used to uniquely identify a volume, or parameters to identify a set of volumes that meet the given set of criteria.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-Partition
```

This example returns all partitions, on all disks.

### EXAMPLE 2
```
PS C:\>Get-Partition -DiskNumber 5
Disk Number: 5 
 
PartitionNumber  DriveLetter Offset                                        Size Type 
---------------  ----------- ------                                        ---- ---- 
1                H           1048576                                  298.09 GB IFS
```

This example returns all partitions on disk 5.

### EXAMPLE 3
```
PS C:\>Get-Partition -DriveLetter C
Disk Number: 0 
 
PartitionNumber  DriveLetter Offset                                        Size Type 
---------------  ----------- ------                                        ---- ---- 
2                C           368050176                                465.42 GB IFS
```

This example returns partitions associated with the volume for drive letter C.

### EXAMPLE 4
```
PS C:\>Get-Partition | Where-Object -FilterScript {$_.Type -Eq "Basic"}
```

This example returns only the basic partitions on all disks.

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

### -Disk
Accepts a Disk object as input.
The Disk CIM object is exposed by the Get-Disk cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByDisk
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DiskId
Specifies an ID used to identify a disk in the system.

```yaml
Type: String[]
Parameter Sets: ById
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskNumber
Specifies the number of the disk.

```yaml
Type: UInt32[]
Parameter Sets: ByNumber
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DriveLetter
Specifies a letter used to identify a drive or volume in the system.
Specifically the drive on which the partition resides.

```yaml
Type: Char[]
Parameter Sets: ByDriveLetter
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Offset
Specifies the starting offset, in bytes.

```yaml
Type: UInt64[]
Parameter Sets: ById
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PartitionNumber
Specifies the number of the partition.

```yaml
Type: UInt32[]
Parameter Sets: ByNumber
Aliases: Number

Required: False
Position: 1
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

### -Volume
Accepts a Volume object as input.
The Volume CIM object is exposed by the Get-Volume cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByVolume
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Disk
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Volume
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Partitions
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Where-Object](https://go.microsoft.com/fwlink/p/?LinkID=113423)

[Get-Disk](./Get-Disk.md)

[Get-Volume](./Get-Volume.md)

