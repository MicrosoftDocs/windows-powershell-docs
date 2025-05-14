---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Partition.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/add-partitionaccesspath?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-PartitionAccessPath
---

# Add-PartitionAccessPath

## SYNOPSIS
Adds an access path such as a drive letter or folder to a partition.

## SYNTAX

### ByUniqueId (Default)
```
Add-PartitionAccessPath [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ById
```
Add-PartitionAccessPath -DiskId <String[]> -Offset <UInt64[]> [[-AccessPath] <String>] [-AssignDriveLetter]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByNumber
```
Add-PartitionAccessPath [-DiskNumber] <UInt32[]> [-PartitionNumber] <UInt32[]> [[-AccessPath] <String>]
 [-AssignDriveLetter] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByDriveLetter
```
Add-PartitionAccessPath -DriveLetter <Char[]> [[-AccessPath] <String>] [-AssignDriveLetter]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Add-PartitionAccessPath -InputObject <CimInstance[]> [[-AccessPath] <String>] [-AssignDriveLetter]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-PartitionAccessPath** cmdlet adds an access path such as a drive letter or folder to a partition.
Access paths can be either a drive letter or a mount point.

## EXAMPLES

### Example 1: Add a drive letter to a partition by disk and partition number
```
PS C:\>Add-PartitionAccessPath -DiskNumber 1 -PartitionNumber 2 -AccessPath F:
```

This example adds the access path F: to partition 2 of disk 1.

## PARAMETERS

### -AccessPath
Assigns an access path to the partition.
An access path can be a drive letter (for example, "C:" or "C:\") or a path to an empty directory on an NTFS volume.
The access path string does not require a trailing backslash.

```yaml
Type: String
Parameter Sets: ById, ByNumber, ByDriveLetter, InputObject (cdxml)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -AssignDriveLetter
Assigns the next available drive letter to the new partition.

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

Required: True
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

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Specifies that the cmdlet should output an object representing the partition to which you added an access path.
By default, this cmdlet does not generate any output.

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
You can pipe a Partition object to the *InputObject* parameter to specify the partition to which you want to add an access path.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Partition
If you specify the *Passthru* parameter, this cmdlet outputs a Partition object representing the partition on which you added an access path.

## NOTES

* Mounted folders are supported only on NTFS-formatted partitions.
* You can only assign a single drive letter to a partition. To change the drive letter, use the **Set-Partition** cmdlet with the *NewDriveLetter* parameter.
* The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects. The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-Partition](./Get-Partition.md)

[Remove-PartitionAccessPath](./Remove-PartitionAccessPath.md)

[Set-Partition](./Set-Partition.md)

