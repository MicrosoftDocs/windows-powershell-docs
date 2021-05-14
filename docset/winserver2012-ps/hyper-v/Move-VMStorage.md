---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/move-vmstorage?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Move-VMStorage

## SYNOPSIS
Moves the storage of a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Move-VMStorage [-VMName] <String> [-DestinationStoragePath] <String> [-AllowUnverifiedPaths] [-AsJob]
 [-ComputerName <String[]>] [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Move-VMStorage [-VMName] <String> [-AllowUnverifiedPaths] [-AsJob] [-ComputerName <String[]>]
 [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource] [-SmartPagingFilePath <String>]
 [-SnapshotFilePath <String>] [-Vhds <Hashtable[]>] [-VirtualMachinePath <String>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Move-VMStorage [-VM] <VirtualMachine> [-DestinationStoragePath] <String> [-AllowUnverifiedPaths] [-AsJob]
 [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Move-VMStorage [-VM] <VirtualMachine> [-AllowUnverifiedPaths] [-AsJob] [-ResourcePoolName <String>]
 [-RetainVhdCopiesOnSource] [-SmartPagingFilePath <String>] [-SnapshotFilePath <String>] [-Vhds <Hashtable[]>]
 [-VirtualMachinePath <String>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Move-VMStorage** cmdlet moves the storage of a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\> Move-VMStorage "Test VM" -DestinationStoragePath D:\TestVM
```

Moves all files associated with a virtual machine test VM to D:\TestVM

### Example 2
```
PS C:\>Move-VMStorage "Test VM" -VirtualMachinePath D:\TestVM\Config -SnapshotFilePath D:\TestVM\Snapshots -SmartPagingFilePath D:\TestVM\SmartPaging -VHDs @(@{"SourceFilePath" = "C:\TestVM\Disk1.VHDX"; "DestinationFilePath" = "D:\TestVM\Disks\Disk1.VHDX"}, @{"SourceFilePath" = "C:\TestVM\Disk2.VHDX"; "DestinationFilePath" = "D:\TestVM\Disks\Disk2.VHDX"})
```

Moves all files associated with a virtual machine test VM to different locations under D:\TestVM.

## PARAMETERS

### -AsJob
Specifies that the cmdlet is to be run as a background job.

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

### -ResourcePoolName
Specifies the name of the storage resource pool to use after the move operation is complete.

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

### -SnapshotFilePath
Specifies the new path for any snapshot files associated with the virtual machine.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine whose storage is to be moved.

```yaml
Type: VirtualMachine
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine whose storage is to be moved.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualMachinePath
Specifies the path to the virtual machine configuration file and associated memory files.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowUnverifiedPaths
Allows the move operation to be attempted even if the paths specified for the destination computer cannot be verified prior to attempting the move operation.

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

### -DestinationStoragePath
Specifies a destination storage path to which all virtual machine storage is to be moved.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetainVhdCopiesOnSource
Specify **$true** to keep any parent virtual hard disks on the source computer.
If not specified, all virtual hard disks will be removed from the source computer once the virtual machine is successfully moved.

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

### -SmartPagingFilePath
Specifies the new path to use for a smart paging file, if one is needed.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vhds
Specifies an array of hashtables that contain locations for each individual virtual hard disk to be moved.
Each hashtable should have two entries.
The first entry specifies the current location of the virtual hard disk to move, and has a key of SourceFilePath.
The second entry specifies the new location for the virtual hard disk, and has a key of DestinationFilePath.
The virtual hard disk name must be identical in both entries.

```yaml
Type: Hashtable[]
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more virtual machine hosts on which the virtual machine storage is to be moved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
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

## OUTPUTS

## NOTES

## RELATED LINKS



