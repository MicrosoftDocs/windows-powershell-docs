---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/compare-vm?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Compare-VM
---

# Compare-VM

## SYNOPSIS
Compares a virtual machine and a virtual machine host for compatibility, returning a compatibility report.

## SYNTAX

### NameSingleDestination (Default)
```
Compare-VM [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-AsJob] [-Name] <String>
 [-DestinationHost] <String> [-DestinationCredential <PSCredential>] [-IncludeStorage]
 [-DestinationStoragePath <String>] [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### NameSingleDestinationAndCimSession
```
Compare-VM [-CimSession <CimSession[]>] [-AsJob] [-Name] <String> [-DestinationCimSession] <CimSession>
 [-IncludeStorage] [-DestinationStoragePath <String>] [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NameMultipleDestinationsAndCimSession
```
Compare-VM [-CimSession <CimSession[]>] -VirtualMachinePath <String> [-SnapshotFilePath <String>]
 [-SmartPagingFilePath <String>] [-AsJob] [-Name] <String> [-DestinationCimSession] <CimSession>
 [-Vhds <Hashtable[]>] [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Register
```
Compare-VM [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-AsJob]
 [-Path] <String> [-Register] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Copy
```
Compare-VM [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VirtualMachinePath <String>] [-SnapshotFilePath <String>] [-SmartPagingFilePath <String>] [-AsJob]
 [-Path] <String> [[-VhdDestinationPath] <String>] [-Copy] [-VhdSourcePath <String>] [-GenerateNewId] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### NameMultipleDestinations
```
Compare-VM [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-VirtualMachinePath <String>]
 [-SnapshotFilePath <String>] [-SmartPagingFilePath <String>] [-AsJob] [-Name] <String>
 [-DestinationHost] <String> [-DestinationCredential <PSCredential>] [-Vhds <Hashtable[]>]
 [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMMultipleDestinations
```
Compare-VM [-VirtualMachinePath <String>] [-SnapshotFilePath <String>] [-SmartPagingFilePath <String>] [-AsJob]
 [-VM] <VirtualMachine> [-DestinationHost] <String> [-DestinationCredential <PSCredential>]
 [-Vhds <Hashtable[]>] [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMMultipleDestinationsAndCimSession
```
Compare-VM -VirtualMachinePath <String> [-SnapshotFilePath <String>] [-SmartPagingFilePath <String>] [-AsJob]
 [-VM] <VirtualMachine> [-DestinationCimSession] <CimSession> [-Vhds <Hashtable[]>]
 [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CompatibilityReport
```
Compare-VM [-CompatibilityReport] <VMCompatibilityReport> [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMSingleDestinationAndCimSession
```
Compare-VM [-AsJob] [-VM] <VirtualMachine> [-DestinationCimSession] <CimSession> [-IncludeStorage]
 [-DestinationStoragePath <String>] [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### VMSingleDestination
```
Compare-VM [-AsJob] [-VM] <VirtualMachine> [-DestinationHost] <String> [-DestinationCredential <PSCredential>]
 [-IncludeStorage] [-DestinationStoragePath <String>] [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Compare-VM** cmdlet compares a virtual machine and a virtual machine host for compatibility, returning a compatibility report.
This is useful when trying to import or migrate a virtual machine that is incompatible with the target server that runs Hyper-V.

## EXAMPLES

### Example 1
```
PS C:\> Compare-VM -Name TestVM -DestinationHost TestDestinationHost
```

Compares virtual machine TestVM and Hyper-V host TestDestinationHost for compatibility.

### Example 2
```
Attempts import of a virtual machine; the attempt fails due to incompatibilities with the Hyper-V host.
PS C:\> Import-VM -Path 'D:\vm1\Virtual Machines\53EAE599-4D3B-4923-B173-6AEA29CB7F42.XML'
Import-VM : Unable to import virtual machine due to configuration errors.  Please use Compare-VM to repair the virtual machine.
At line:1 char:1
+ import-vm -Path 'D:\vm1\Virtual Machines\53EAE599-4D3B-4923-B173-6AEA29CB7F42.XM ...
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [Import-VM], VirtualizationOperationFailedException
    + FullyQualifiedErrorId : Microsoft.HyperV.PowerShell.Commands.ImportVMCommand

Gets a compatibility report that describes the attempted import and lists the virtual machine's incompatibilities with the Hyper-V host.
PS C:\> $report = Compare-VM -Path 'D:\vm1\Virtual Machines\53EAE599-4D3B-4923-B173-6AEA29CB7F42.XML'


Displays the compatibility report, revealing that the virtual network adapter was connected to switch Production. The Hyper-V host has no switch by that name.
PS C:\> $report.Incompatibilities | Format-Table -AutoSize
Message                                      MessageId Source
-------                                      --------- ------
Could not find Ethernet switch 'Production'.     33012 Microsoft.HyperV.PowerShell.VMNetworkAdapter

Disconnects the virtual network adapter.
PS C:\> $report.Incompatibilities[0].Source | Disconnect-VMNetworkAdapter


Generates a new compatibility report to determine if the virtual machine is compatible with the Hyper-V host.
PS C:\> Compare-VM -CompatibilityReport $report


Displays the compatibility report.
PS C:\> $report
VM                 : Microsoft.HyperV.PowerShell.VirtualMachine
OperationType      : ImportVirtualMachine
Destination        : HYPER-V-1
Path               : D:\vm1\Virtual Machines\53EAE599-4D3B-4923-B173-6AEA29CB7F42.XML
SnapshotPath       : D:\vm1\Snapshots
VhdDestinationPath :
VhdSourcePath      :
Incompatibilities  :

Imports the virtual machine.
PS C:\> import-vm -CompatibilityReport $report
Name State CPUUsage(%) MemoryAssigned(M) MemoryDemand(M) MemoryStatus Uptime   Status             ReplicationState
---- ----- ----------- ----------------- --------------- ------------ ------   ------             ----------------
VM1  Off   0           0                 0                            00:00:00 Operating normally Disabled
```

Imports a virtual machine whose configuration is not compatible with the Hyper-V host.
Note the use of **Compare-VM** to troubleshoot the import failure in the first step.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: NameSingleDestinationAndCimSession, NameMultipleDestinationsAndCimSession, Register, Copy
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CompatibilityReport
Specifies a compatibility report which resolves any incompatibilities between the virtual machine and the virtual machine host.

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
Specifies one or more Hyper-v hosts that run this cmdlet.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: NameSingleDestination, Register, Copy, NameMultipleDestinations
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

### -Copy
Specifies that the comparison should be made for a copy import operation.

```yaml
Type: SwitchParameter
Parameter Sets: Copy
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: NameSingleDestination, Register, Copy, NameMultipleDestinations
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationCimSession
Specifies the **CIMSession** on the Hyper-V host to which this cmdlet compares the virtual machine for compatibility.

```yaml
Type: CimSession
Parameter Sets: NameSingleDestinationAndCimSession, NameMultipleDestinationsAndCimSession, VMMultipleDestinationsAndCimSession, VMSingleDestinationAndCimSession
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
Parameter Sets: NameSingleDestination, NameMultipleDestinations, VMMultipleDestinations, VMSingleDestination
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationHost
Specifies the Hyper-V host to which the virtual machine is to be compared for compatibility.

```yaml
Type: String
Parameter Sets: NameSingleDestination, NameMultipleDestinations, VMMultipleDestinations, VMSingleDestination
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
Parameter Sets: NameSingleDestination, NameSingleDestinationAndCimSession, VMSingleDestinationAndCimSession, VMSingleDestination
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GenerateNewId
Specifies that the virtual machine should be copied and given a new unique identifier.

```yaml
Type: SwitchParameter
Parameter Sets: Copy
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeStorage
Specifies that the compatibility comparison should include both the virtual machine and its storage.

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
Specifies the name of the virtual machine to be compared.

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

### -Path
Specifies the path to the configuration file of the virtual machine to be compared.

```yaml
Type: String
Parameter Sets: Register, Copy
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Register
Specifies that the comparison should be made for an in-place import operation.

```yaml
Type: SwitchParameter
Parameter Sets: Register
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourcePoolName
Specifies the friendly name of the resource pool.

```yaml
Type: String
Parameter Sets: NameSingleDestination, NameSingleDestinationAndCimSession, NameMultipleDestinationsAndCimSession, NameMultipleDestinations, VMMultipleDestinations, VMMultipleDestinationsAndCimSession, VMSingleDestinationAndCimSession, VMSingleDestination
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
Parameter Sets: NameSingleDestination, NameSingleDestinationAndCimSession, NameMultipleDestinationsAndCimSession, NameMultipleDestinations, VMMultipleDestinations, VMMultipleDestinationsAndCimSession, VMSingleDestinationAndCimSession, VMSingleDestination
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
Parameter Sets: NameMultipleDestinationsAndCimSession, Copy, NameMultipleDestinations, VMMultipleDestinations, VMMultipleDestinationsAndCimSession
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
Parameter Sets: NameMultipleDestinationsAndCimSession, Copy, NameMultipleDestinations, VMMultipleDestinations, VMMultipleDestinationsAndCimSession
Aliases: CheckpointFileLocation, SnapshotFileLocation

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies a virtual machine.

```yaml
Type: VirtualMachine
Parameter Sets: VMMultipleDestinations, VMMultipleDestinationsAndCimSession, VMSingleDestinationAndCimSession, VMSingleDestination
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VhdDestinationPath
Specifies the folder to which the virtual machine's VHD is to be copied.

```yaml
Type: String
Parameter Sets: Copy
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VhdSourcePath
Specifies the folder from which the virtual machine's VHD files are to be copied.

```yaml
Type: String
Parameter Sets: Copy
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vhds
Specifies an array of hash tables that specifies a location for each individual virtual hard disk that needs to be compared.
Each hash table has two entries.
The first entry specifies the current location of the virtual hard disk to move, and has a key of **SourceFilePath**.
The second entry specifies the new location for the virtual hard disk, and has a key of **DestinationFilePath**.
The virtual hard disk names must be identical in both entries.

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
Specifies the path where the resulting virtual machine configuration files are to be stored.

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
Parameter Sets: Copy, NameMultipleDestinations, VMMultipleDestinations
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

### Microsoft.HyperV.PowerShell.VMCompatibilityReport

## NOTES

## RELATED LINKS

