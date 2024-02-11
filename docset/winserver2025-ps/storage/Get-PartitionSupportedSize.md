---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Partition.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-partitionsupportedsize?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PartitionSupportedSize
---

# Get-PartitionSupportedSize

## SYNOPSIS
Returns information on supported partition sizes for the specified Disk object.

## SYNTAX

### ByUniqueId (Default)
```
Get-PartitionSupportedSize [<CommonParameters>]
```

### ById
```
Get-PartitionSupportedSize -DiskId <String[]> [-Offset <UInt64[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByNumber
```
Get-PartitionSupportedSize [-DiskNumber] <UInt32[]> [[-PartitionNumber] <UInt32[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByDriveLetter
```
Get-PartitionSupportedSize -DriveLetter <Char[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Get-PartitionSupportedSize -InputObject <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-PartitionSupportedSize** cmdlet returns information on supported partition sizes for the specified Disk object.

## EXAMPLES

### Example 1
```
PS C:\>Get-PartitionSupportedSize -DiskNumber 3 -PartitionNumber 2
SizeMin                                                 SizeMax
-----------                                             -----------
```

This command will show the minimum and maximum size of the partition (SizeMin and SizeMax).

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

```yaml
Type: SwitchParameter
Parameter Sets: ById, ByNumber, ByDriveLetter, InputObject (cdxml)
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
Parameter Sets: ById, ByNumber, ByDriveLetter, InputObject (cdxml)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskId
Specifies an ID used to identify a disk in the system.

```yaml
Type: String[]
Parameter Sets: ById
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskNumber
Specifies an array of disk numbers.
These represent the disks for which to get partitions.

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

### -DriveLetter
Specifies a letter used to identify a drive or volume in the system.

```yaml
Type: Char[]
Parameter Sets: ByDriveLetter
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: ById, ByNumber, ByDriveLetter, InputObject (cdxml)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Partition
You can pipe a Partition object to the **InputObject** parameter.

## OUTPUTS

### System.UInt64

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

* This cmdlet starts the "Optimize Drive" (`defragsvc`) service. This could lead to longer execution time on larger fragmented drives.

## RELATED LINKS

[Get-Partition](./Get-Partition.md)

