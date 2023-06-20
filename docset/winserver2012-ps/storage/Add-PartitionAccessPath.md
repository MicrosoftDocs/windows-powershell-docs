---
external help file: Storage2_Cmdlets.xml
Module Name: Storage
online version: https://learn.microsoft.com/powershell/module/storage/add-partitionaccesspath?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-PartitionAccessPath

## SYNOPSIS
Adds an access path such as a drive letter or folder to a partition.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-PartitionAccessPath [-DiskNumber] <UInt32[]> [-PartitionNumber] <UInt32[]> [[-AccessPath] <String>]
 [-AsJob] [-AssignDriveLetter] [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Add-PartitionAccessPath [[-AccessPath] <String>] [-AsJob] [-AssignDriveLetter] [-CimSession <CimSession[]>]
 [-PassThru] [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Add-PartitionAccessPath [[-AccessPath] <String>] [-AsJob] [-AssignDriveLetter] [-CimSession <CimSession[]>]
 [-PassThru] [-ThrottleLimit <Int32>] -DriveLetter <Char[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Add-PartitionAccessPath [[-AccessPath] <String>] [-AsJob] [-AssignDriveLetter] [-CimSession <CimSession[]>]
 [-PassThru] [-ThrottleLimit <Int32>] -DiskId <String[]> -Offset <UInt64[]> [-Confirm] [-WhatIf]
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
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
Assigns the next available drive letter to the new partition.

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
Specifies an ID used to identify a disk in the system.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

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

### -DriveLetter
Specifies a letter used to identify a drive or volume in the system.

```yaml
Type: Char[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Accepts a Partition object from the pipeline as input.
Enter a Partition CIM object, which you can get by using the Get-Partition cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_4
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: Number

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Specifies that the cmdlet should output an object representing the partition to which you added an access path.
By default, this cmdlet does not generate any output.

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Partition
You can pipe a Partition object to the **InputObject** parameter to specify the partition to which you want to add an access path.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Partition
If you specify the **Passthru** parameter, this cmdlet outputs a Partition object representing the partition on which you added an access path.

## NOTES
* Mounted folders are supported only on NTFS-formatted partitions.
* You can only assign a single drive letter to a partition. To change the drive letter, use the **Set-Partition** cmdlet with the **NewDriveLetter** parameter.
* The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects. The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## RELATED LINKS

[Get-Partition](./Get-Partition.md)

[Remove-PartitionAccessPath](./Remove-PartitionAccessPath.md)

[Set-Partition](./Set-Partition.md)

