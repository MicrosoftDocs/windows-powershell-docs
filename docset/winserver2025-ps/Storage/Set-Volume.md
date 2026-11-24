---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageCmdlets.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/set-volume?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Volume
---

# Set-Volume

## SYNOPSIS
Sets or changes the file system label of an existing volume.

## SYNTAX

### ByDriveLetterSetLabel (Default)
```
Set-Volume [-NewFileSystemLabel <String>] -DriveLetter <Char> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectSetDedup
```
Set-Volume -InputObject <CimInstance[]> [-DedupMode <DedupMode>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectSetLabel
```
Set-Volume -InputObject <CimInstance[]> [-NewFileSystemLabel <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByLabelSetLabel
```
Set-Volume [-NewFileSystemLabel <String>] -FileSystemLabel <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByPathSetLabel
```
Set-Volume [-NewFileSystemLabel <String>] -Path <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByUniqueIdSetLabel
```
Set-Volume [-NewFileSystemLabel <String>] -UniqueId <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueIdSetDedup
```
Set-Volume -UniqueId <String> [-DedupMode <DedupMode>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByPathSetDedup
```
Set-Volume -Path <String> [-DedupMode <DedupMode>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByLabelSetDedup
```
Set-Volume -FileSystemLabel <String> [-DedupMode <DedupMode>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByDriveLetterSetDedup
```
Set-Volume -DriveLetter <Char> [-DedupMode <DedupMode>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Set-Volume** cmdlet sets or changes the file system label of an existing volume.

## EXAMPLES

### Example 1: Set the file system label
```
PS C:\>Set-Volume -FileSystemLabel "Test" -NewFileSystemLabel "TestData"
```

This example changes the file system label from test to TestData.

### Example 2: Format the volume
```
PS C:\>Format-Volume -InputObject $PartitionObject -FileSystem NTFS -NewFileSystemLabel "TestData" -ClusterSize (8K) -ShortFileNameSupport $False
```

This example uses the specified Partition object as an input to format the volume on this partition with the NTFS file system, using the file system label testdata with a cluster size of 8K, and with short filename support disabled.

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

### -DedupMode
Specifies the Data Deduplication mode to use for the volume, if Data Deduplication is enabled on this volume.
The acceptable values for this parameter are:

- Backup
- Disabled
- GeneralPurpose
- Hyper-V
- NotAvailable

```yaml
Type: DedupMode
Parameter Sets: ByObjectSetDedup, ByUniqueIdSetDedup, ByPathSetDedup, ByLabelSetDedup, ByDriveLetterSetDedup
Aliases:
Accepted values: Disabled, GeneralPurpose, HyperV, Backup, NotAvailable

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DriveLetter
Specifies a letter used to identify a drive or volume in the system.

```yaml
Type: Char
Parameter Sets: ByDriveLetterSetLabel, ByDriveLetterSetDedup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -FileSystemLabel
Specifies the file system label of the object.
The acceptable values for this parameter include: NTFS and ReFS.

```yaml
Type: String
Parameter Sets: ByLabelSetLabel, ByLabelSetDedup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: ByObjectSetDedup, ByObjectSetLabel
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NewFileSystemLabel
Specifies a new file system label to use.

```yaml
Type: String
Parameter Sets: ByDriveLetterSetLabel, ByObjectSetLabel, ByLabelSetLabel, ByPathSetLabel, ByUniqueIdSetLabel
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Contains valid path information.

```yaml
Type: String
Parameter Sets: ByPathSetLabel, ByPathSetDedup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -UniqueId
Specifies a unique ID.

```yaml
Type: String
Parameter Sets: ByUniqueIdSetLabel, ByUniqueIdSetDedup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Partition
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Volume
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Partition
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Volume
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Format-Volume](./Format-Volume.md)

[Get-Volume](./Get-Volume.md)

[Optimize-Volume](./Optimize-Volume.md)

[Repair-Volume](./Repair-Volume.md)

