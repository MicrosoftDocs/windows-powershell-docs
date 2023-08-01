---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/hyper-v/move-vm?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Move-VM
---

# Move-VM

## SYNOPSIS
Moves a virtual machine to a new Hyper-V host.

## SYNTAX

### Name (Default)
```
Move-VM [-ComputerName <String[]>] [-Name] <String> [-DestinationHost] <String> [-IncludeStorage]
 [-DestinationStoragePath <String>] [-VirtualMachinePath <String>] [-SnapshotFilePath <String>]
 [-SmartPagingFilePath <String>] [-Vhds <Hashtable[]>] [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource]
 [-AsJob] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CompatibilityReport
```
Move-VM [-CompatibilityReport] <VMCompatibilityReport> [-AsJob] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VM
```
Move-VM [-VM] <VirtualMachine> [-DestinationHost] <String> [-IncludeStorage] [-DestinationStoragePath <String>]
 [-VirtualMachinePath <String>] [-SnapshotFilePath <String>] [-SmartPagingFilePath <String>]
 [-Vhds <Hashtable[]>] [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource] [-AsJob] [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Move-VM** cmdlet moves a virtual machine to a new Hyper-V host.

## EXAMPLES

### Example 1: Move VM to remote computer
```powershell
PS C:\> Move-VM -Name "Test VM" -DestinationHost remoteServer
```

Moves a virtual machine test VM to a remote computer remoteServer when the virtual machine is stored on an SMB share.

### Example 2: Move VM and all storage to remote computer
```powershell
PS C:\> Move-VM -Name "Test VM" -DestinationHost remoteServer -IncludeStorage -DestinationStoragePath D:\TestVM
```

Moves virtual machine test VM to remote computer remoteServer, and moves all files associated with the virtual machine to D:\TestVM on the remote computer.

### Example 3: Move VM and specified storage file to remote computer
```powershell
PS C:\> Move-VM  -Name "Test VM" -DestinationHost remoteServer -VirtualMachinePath D:\TestVM\Config -SnapshotFilePath D:\TestVM\Snapshots -SmartPagingFilePath D:\TestVM\SmartPaging -IncludeStorage -VHDs @(@{"SourceFilePath" = "C:\TestVM\Disk1.VHDX"; "DestinationFilePath" = "D:\TestVM\Disks\Disk1.VHDX"}, @{"SourceFilePath" = "C:\TestVM\Disk2.VHDX"; "DestinationFilePath" = "D:\TestVM\Disks\Disk2.VHDX"})
```

Moves a virtual machine Test VM to a remote computer remoteServer and places the files associated with the virtual machine in the specified locations under D:\TestVM on the remote computer.

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

### -CompatibilityReport
Specifies a compatibility report which includes any adjustments required for the move.

```yaml
Type: VMCompatibilityReport
Parameter Sets: CompatibilityReport
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts from which the virtual machine is to be removed.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: Name
Aliases:

Required: False
Position: Named
Default value: .
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

### -DestinationHost
Specifies the virtual machine host to which the virtual machine is to be moved.

```yaml
Type: String
Parameter Sets: Name, VM
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationStoragePath
Specifies a destination storage path to which all virtual machine storage is to be moved.

```yaml
Type: String
Parameter Sets: Name, VM
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeStorage
Specifies that both the virtual machine and its storage are to be moved.

```yaml
Type: SwitchParameter
Parameter Sets: Name, VM
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the friendly name of the virtual machine to be moved.

```yaml
Type: String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Passthru
Specifies that an object is to be passed through to be pipeline representing the moved virtual machine.

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
Parameter Sets: Name, VM
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
Parameter Sets: Name, VM
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
Parameter Sets: Name, VM
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
Parameter Sets: Name, VM
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine to be moved.

```yaml
Type: VirtualMachine
Parameter Sets: VM
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Vhds
An array of hashtables that specifies a location for each individual virtual hard disk that needs to be moved.
Each hashtable has two entries.
The first entry specifies the current location of the virtual hard disk to move, and has a key of SourceFilePath.
The second entry specifies the new location for the virtual hard disk, and has a key of DestinationFilePath.
The virtual hard disk names must be identical in both entries.

```yaml
Type: Hashtable[]
Parameter Sets: Name, VM
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualMachinePath
Specifies the path for the virtual machine configuration file and associated memory files.

```yaml
Type: String
Parameter Sets: Name, VM
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

### 
None, by default.
**Microsoft.HyperV.PowerShell.VirtualMachine** if the migration succeeds and **-PassThru** is specified.
**Microsoft.HyperV.PowerShell.CompatibilityReport** if the migration fails because of an incompatibility.

## NOTES

## RELATED LINKS

