---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/move-vmstorage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Move-VMStorage
---

# Move-VMStorage

## SYNOPSIS
Moves the storage of a virtual machine.

## SYNTAX

### NameSingleDestination (Default)
```
Move-VMStorage [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-Name] <String> [-DestinationStoragePath] <String> [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource]
 [-RemoveSourceUnmanagedVhds] [-AllowUnverifiedPaths] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NameMultipleDestinations
```
Move-VMStorage [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-Name] <String> [-VirtualMachinePath <String>] [-SnapshotFilePath <String>] [-SmartPagingFilePath <String>]
 [-Vhds <Hashtable[]>] [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource] [-RemoveSourceUnmanagedVhds]
 [-AllowUnverifiedPaths] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMSingleDestination
```
Move-VMStorage [-VM] <VirtualMachine> [-DestinationStoragePath] <String> [-ResourcePoolName <String>]
 [-RetainVhdCopiesOnSource] [-RemoveSourceUnmanagedVhds] [-AllowUnverifiedPaths] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMMultipleDestinations
```
Move-VMStorage [-VM] <VirtualMachine> [-VirtualMachinePath <String>] [-SnapshotFilePath <String>]
 [-SmartPagingFilePath <String>] [-Vhds <Hashtable[]>] [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource]
 [-RemoveSourceUnmanagedVhds] [-AllowUnverifiedPaths] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
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
PS C:\> Move-VMStorage "Test VM" -VirtualMachinePath D:\TestVM\Config -SnapshotFilePath D:\TestVM\Snapshots -SmartPagingFilePath D:\TestVM\SmartPaging -VHDs @(@{"SourceFilePath" = "C:\TestVM\Disk1.VHDX"; "DestinationFilePath" = "D:\TestVM\Disks\Disk1.VHDX"}, @{"SourceFilePath" = "C:\TestVM\Disk2.VHDX"; "DestinationFilePath" = "D:\TestVM\Disks\Disk2.VHDX"})
```

Moves all files associated with a virtual machine test VM to different locations under D:\TestVM.

## PARAMETERS

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

### -AsJob
Runs the cmdlet as a background job.

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
Parameter Sets: NameSingleDestination, NameMultipleDestinations
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
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: NameSingleDestination, NameMultipleDestinations
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
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: NameSingleDestination, NameMultipleDestinations
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
Parameter Sets: NameSingleDestination, VMSingleDestination
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a name.

```yaml
Type: String
Parameter Sets: NameSingleDestination, NameMultipleDestinations
Aliases: VMName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RemoveSourceUnmanagedVhds
Indicates that Hyper-V deletes the parent virtual hard disk on the source after this cmdlet moves a differencing virtual hard disk, when the migration is finished.

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
Parameter Sets: NameMultipleDestinations, VMMultipleDestinations
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
Parameter Sets: NameMultipleDestinations, VMMultipleDestinations
Aliases: CheckpointFileLocation, SnapshotFileLocation

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
Parameter Sets: VMSingleDestination, VMMultipleDestinations
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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
Parameter Sets: NameMultipleDestinations, VMMultipleDestinations
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualMachinePath
Specifies the path to the virtual machine configuration file and associated memory files.

```yaml
Type: String
Parameter Sets: NameMultipleDestinations, VMMultipleDestinations
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

## OUTPUTS

## NOTES

## RELATED LINKS

