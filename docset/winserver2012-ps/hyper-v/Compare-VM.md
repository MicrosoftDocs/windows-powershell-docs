---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/compare-vm?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Compare-VM

## SYNOPSIS
Compares a virtual machine and a virtual machine host for compatibility, returning a compatibility report.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Compare-VM [-Name] <String> [-DestinationHost] <String> [-AsJob] [-ComputerName <String[]>]
 [-DestinationStoragePath <String>] [-IncludeStorage] [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource]
 [-SmartPagingFilePath <String>] [-SnapshotFilePath <String>] [-Vhds <Hashtable[]>]
 [-VirtualMachinePath <String>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Compare-VM [-CompatibilityReport] <VMCompatibilityReport> [-AsJob] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Compare-VM [-Path] <String> [-AsJob] [-ComputerName <String[]>] [-Register] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Compare-VM [-Path] <String> [[-VhdDestinationPath] <String>] [-AsJob] [-ComputerName <String[]>]
 [-GenerateNewId] [-SmartPagingFilePath <String>] [-SnapshotFilePath <String>] [-VhdSourcePath <String>]
 [-VirtualMachinePath <String>] [-Copy] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Compare-VM [-VM] <VirtualMachine> [-DestinationHost] <String> [-AsJob] [-DestinationStoragePath <String>]
 [-IncludeStorage] [-ResourcePoolName <String>] [-RetainVhdCopiesOnSource] [-SmartPagingFilePath <String>]
 [-SnapshotFilePath <String>] [-Vhds <Hashtable[]>] [-VirtualMachinePath <String>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Compare-VM** cmdlet compares a virtual machine and a virtual machine host for compatibility, returning a compatibility report.
This is useful when trying to import or migrate a virtual machine that is incompatible with the target Hyper-V server.

## EXAMPLES

### Example 1
```
PS C:\>Compare-VM -Name TestVM -DestinationHost TestDestinationHost
```

Compares virtual machine TestVM and Hyper-V host TestDestinationHost for compatibility.

### Example 2
```
Attempts import of a virtual machine; the attempt fails due to incompatibilities with the Hyper-V host.
PS C:\>Import-VM -Path 'D:\vm1\Virtual Machines\53EAE599-4D3B-4923-B173-6AEA29CB7F42.XML'
Import-VM : Unable to import virtual machine due to configuration errors.  Please use Compare-VM to repair the virtual machine.
At line:1 char:1
+ import-vm -Path 'D:\vm1\Virtual Machines\53EAE599-4D3B-4923-B173-6AEA29CB7F42.XM ...
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [Import-VM], VirtualizationOperationFailedException
    + FullyQualifiedErrorId : Microsoft.HyperV.PowerShell.Commands.ImportVMCommand 

Gets a compatibility report that describes the attempted import and lists the virtual machine's incompatibilities with the Hyper-V host.
PS C:\>$report = Compare-VM -Path 'D:\vm1\Virtual Machines\53EAE599-4D3B-4923-B173-6AEA29CB7F42.XML'


Displays the compatibility report, revealing that the virtual network adapter was connected to switch Production. The Hyper-V host has no switch by that name.
PS C:\>$report.Incompatibilities | Format-Table -AutoSize
Message                                      MessageId Source
-------                                      --------- ------
Could not find Ethernet switch 'Production'.     33012 Microsoft.HyperV.PowerShell.VMNetworkAdapter 

Disconnects the virtual network adapter.
PS C:\>$report.Incompatibilities[0].Source | Disconnect-VMNetworkAdapter


Generates a new compatibility report to determine if the virtual machine is compatible with the Hyper-V host.
PS C:\>Compare-VM -CompatibilityReport $report


Displays the compatibility report.
PS C:\>$report
VM                 : Microsoft.HyperV.PowerShell.VirtualMachine
OperationType      : ImportVirtualMachine
Destination        : HYPER-V-1
Path               : D:\vm1\Virtual Machines\53EAE599-4D3B-4923-B173-6AEA29CB7F42.XML
SnapshotPath       : D:\vm1\Snapshots
VhdDestinationPath :
VhdSourcePath      :
Incompatibilities  :

Imports the virtual machine.
PS C:\>import-vm -CompatibilityReport $report
Name State CPUUsage(%) MemoryAssigned(M) MemoryDemand(M) MemoryStatus Uptime   Status             ReplicationState
---- ----- ----------- ----------------- --------------- ------------ ------   ------             ----------------
VM1  Off   0           0                 0                            00:00:00 Operating normally Disabled
```

Imports a virtual machine whose configuration is not compatible with the Hyper-V host.
Note the use of **Compare-VM** to troubleshoot the import failure in the first step.

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
Specifies a compatibility report which resolves any incompatibilities between the virtual machine and the virtual machine host.

```yaml
Type: VMCompatibilityReport
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the .
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationHost
Specifies the Hyper-V host to which the virtual machine is to be compared for compatibility.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationStoragePath
Specifies a destination storage path to which all virtual machine storage is to be moved.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_5
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
Parameter Sets: UNNAMED_PARAMETER_SET_4
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_5
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Path
Specifies the path to the configuration file of the virtual machine to be compared.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine object to be compared.

```yaml
Type: VirtualMachine
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourcePoolName
Friendly name of the resource pool

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetainVhdCopiesOnSource
Specify this parameter to retain parent virtual hard disks on the source computer.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_5
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_5
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Copy
Specifies that the comparison should be made for a copy import operation.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Register
Specifies that the comparison should be made for an in-place import operation.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VhdDestinationPath
Specifies the folder to which the virtual machine's VHD files are to be copied.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VhdSourcePath
Specifies the folder from which the virtual machine's VHD files are to be copied.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_4
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

### Microsoft.Virtualization.Powershell.CompatibilityReport

## NOTES

## RELATED LINKS



