---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/move-vm?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Move-VM
---

# Move-VM

## SYNOPSIS
Moves a virtual machine to a new Hyper-V host.

## SYNTAX

### NameSingleDestination (Default)
```
Move-VM [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-Name] <String> [-DestinationHost] <String>
 [-DestinationCredential <PSCredential>] [-IncludeStorage] [-DestinationStoragePath <String>]
 [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource] [-RemoveSourceUnmanagedVhds] [-AsJob] [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NameSingleDestinationAndCimSession
```
Move-VM [-CimSession <CimSession[]>] [-Name] <String> [-DestinationCimSession] <CimSession> [-IncludeStorage]
 [-DestinationStoragePath <String>] [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource]
 [-RemoveSourceUnmanagedVhds] [-AsJob] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NameMultipleDestinationsAndCimSession
```
Move-VM [-CimSession <CimSession[]>] [-Name] <String> [-DestinationCimSession] <CimSession>
 -VirtualMachinePath <String> [-SnapshotFilePath <String>] [-SmartPagingFilePath <String>]
 [-Vhds <Hashtable[]>] [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource] [-RemoveSourceUnmanagedVhds]
 [-AsJob] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NameMultipleDestinations
```
Move-VM [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-Name] <String> [-DestinationHost] <String>
 [-DestinationCredential <PSCredential>] [-VirtualMachinePath <String>] [-SnapshotFilePath <String>]
 [-SmartPagingFilePath <String>] [-Vhds <Hashtable[]>] [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource]
 [-RemoveSourceUnmanagedVhds] [-AsJob] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CompatibilityReport
```
Move-VM [-CompatibilityReport] <VMCompatibilityReport> [-AsJob] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMSingleDestinationAndCimSession
```
Move-VM [-VM] <VirtualMachine> [-DestinationCimSession] <CimSession> [-IncludeStorage]
 [-DestinationStoragePath <String>] [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource]
 [-RemoveSourceUnmanagedVhds] [-AsJob] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMSingleDestination
```
Move-VM [-VM] <VirtualMachine> [-DestinationHost] <String> [-DestinationCredential <PSCredential>]
 [-IncludeStorage] [-DestinationStoragePath <String>] [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource]
 [-RemoveSourceUnmanagedVhds] [-AsJob] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMMultipleDestinations
```
Move-VM [-VM] <VirtualMachine> [-DestinationHost] <String> [-DestinationCredential <PSCredential>]
 [-VirtualMachinePath <String>] [-SnapshotFilePath <String>] [-SmartPagingFilePath <String>]
 [-Vhds <Hashtable[]>] [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource] [-RemoveSourceUnmanagedVhds]
 [-AsJob] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMMultipleDestinationsAndCimSession
```
Move-VM [-VM] <VirtualMachine> [-DestinationCimSession] <CimSession> -VirtualMachinePath <String>
 [-SnapshotFilePath <String>] [-SmartPagingFilePath <String>] [-Vhds <Hashtable[]>]
 [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource] [-RemoveSourceUnmanagedVhds] [-AsJob] [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
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
Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: NameSingleDestinationAndCimSession, NameMultipleDestinationsAndCimSession
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
Specifies one or more Hyper-V hosts that run this cmdlet.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
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

### -DestinationCimSession
Specifies the **CIMSession** on the Hyper-V host to which the virtual machine is to be moved.

```yaml
Type: CimSession
Parameter Sets: NameSingleDestinationAndCimSession, NameMultipleDestinationsAndCimSession, VMSingleDestinationAndCimSession, VMMultipleDestinationsAndCimSession
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationCredential
Specifies a user account that has permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential
Parameter Sets: NameSingleDestination, NameMultipleDestinations, VMSingleDestination, VMMultipleDestinations
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationHost
Specifies the Hyper-V host to which the virtual machine is to be moved.

```yaml
Type: String
Parameter Sets: NameSingleDestination, NameMultipleDestinations, VMSingleDestination, VMMultipleDestinations
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationStoragePath
Specifies a destination path to which all virtual machine data is to be moved.

```yaml
Type: String
Parameter Sets: NameSingleDestination, NameSingleDestinationAndCimSession, VMSingleDestinationAndCimSession, VMSingleDestination
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
Parameter Sets: NameSingleDestination, NameSingleDestinationAndCimSession, VMSingleDestinationAndCimSession, VMSingleDestination
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
Parameter Sets: NameSingleDestination, NameSingleDestinationAndCimSession, NameMultipleDestinationsAndCimSession, NameMultipleDestinations
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

### -RemoveSourceUnmanagedVhds
Indicates that Hyper-V deletes the parent virtual hard disk on the source after this cmdlet moves a differencing virtual hard disk, when the migration is finished.

```yaml
Type: SwitchParameter
Parameter Sets: NameSingleDestination, NameSingleDestinationAndCimSession, NameMultipleDestinationsAndCimSession, NameMultipleDestinations, VMSingleDestinationAndCimSession, VMSingleDestination, VMMultipleDestinations, VMMultipleDestinationsAndCimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourcePoolName
Specifies the name of the processor resource pool to be used.

```yaml
Type: String
Parameter Sets: NameSingleDestination, NameSingleDestinationAndCimSession, NameMultipleDestinationsAndCimSession, NameMultipleDestinations, VMSingleDestinationAndCimSession, VMSingleDestination, VMMultipleDestinations, VMMultipleDestinationsAndCimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetainVhdCopiesOnSource
Indicates that this cmdlet retains parent virtual hard disks on the source computer.

```yaml
Type: SwitchParameter
Parameter Sets: NameSingleDestination, NameSingleDestinationAndCimSession, NameMultipleDestinationsAndCimSession, NameMultipleDestinations, VMSingleDestinationAndCimSession, VMSingleDestination, VMMultipleDestinations, VMMultipleDestinationsAndCimSession
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
Parameter Sets: NameMultipleDestinationsAndCimSession, NameMultipleDestinations, VMMultipleDestinations, VMMultipleDestinationsAndCimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SnapshotFilePath
Specifies the path for any snapshot files associated with the virtual machine.

```yaml
Type: String
Parameter Sets: NameMultipleDestinationsAndCimSession, NameMultipleDestinations, VMMultipleDestinations, VMMultipleDestinationsAndCimSession
Aliases: CheckpointFileLocation, SnapshotFileLocation

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
Parameter Sets: VMSingleDestinationAndCimSession, VMSingleDestination, VMMultipleDestinations, VMMultipleDestinationsAndCimSession
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
The first entry specifies the current location of the virtual hard disk to move, and has a key of **SourceFilePath**.
The second entry specifies the new location for the virtual hard disk, and has a key of **DestinationFilePath**.
The virtual hard disk name must be identical in both entries.

```yaml
Type: Hashtable[]
Parameter Sets: NameMultipleDestinationsAndCimSession, NameMultipleDestinations, VMMultipleDestinations, VMMultipleDestinationsAndCimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualMachinePath
Specifies the path where the virtual machine configuration files are to be stored.

```yaml
Type: String
Parameter Sets: NameMultipleDestinationsAndCimSession, VMMultipleDestinationsAndCimSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### None

By default, this cmdlet doesn't return any output.

### Microsoft.HyperV.PowerShell.VirtualMachine

When you use the **PassThru** parameter, this cmdlet returns a **Microsoft.HyperV.PowerShell.VirtualMachine** object if the migration is successful.

### Microsoft.HyperV.PowerShell.CompatibilityReport

When you use the **PassThru** parameter, this cmdlet returns a **Microsoft.HyperV.PowerShell.CompatibilityReport** object if the migration fails because of an incompatibility.

## NOTES

## RELATED LINKS
