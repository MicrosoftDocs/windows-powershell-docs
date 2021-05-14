---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/hyper-v/import-vm?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-VM
---

# Import-VM

## SYNOPSIS
Imports a virtual machine from a file.

## SYNTAX

### Register (Default)
```
Import-VM [-ComputerName <String[]>] [-Path] <String> [-Register] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Copy
```
Import-VM [-ComputerName <String[]>] [-Path] <String> [[-VhdDestinationPath] <String>] [-Copy]
 [-VirtualMachinePath <String>] [-SnapshotFilePath <String>] [-SmartPagingFilePath <String>]
 [-VhdSourcePath <String>] [-GenerateNewId] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CompatibilityReport
```
Import-VM [-CompatibilityReport] <VMCompatibilityReport> [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Import-VM** cmdlet imports a virtual machine from a file.

## EXAMPLES

### Example 1
```
PS C:\>Import-VM -Path 'D:\Test\VirtualMachines\5AE40946-3A98-428E-8C83-081A3C6BD18C.XML'
```

Imports the virtual machine from its configuration file.
The virtual machine is registered in-place, so its files are not copied.

### Example 2
```
PS C:\>Import-VM -Path 'D:\Test2\Virtual Machines\8F148B6D-C674-413E-9FCC-4FBED185C52D.XML' -Copy -GenerateNewId
```

Imports the virtual machine by copying its files to the default virtual machine and virtual hard drive storage locations of the Hyper-V host.
The imported virtual machine will be given a new unique identifier, not the one in the configuration file.
This is useful when you want to import multiple copies of a virtual machine, since each virtual machine must have a unique identifier.

### Example 3
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
Specifies a compatibility report which resolves any incompatibilities between the virtual machine and the Hyper-V host.

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
Specifies one or more Hyper-V hosts from which the virtual machine is to be imported.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: Register, Copy
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

### -Copy
Specifies that the imported virtual machine's files should be copied to the server's default locations, as opposed to registering the virtual machine in-place.

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

### -GenerateNewId
Specifies that the imported virtual machine should be copied and given a new unique identifier.
(By default, **Import-VM** gives the new virtual machine the same unique identifier as the imported virtual machine.)

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

### -Path
Specifies the path to the exported virtual machine to be imported.

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
Specifies that the imported virtual machine is to be registered in-place, as opposed to copying its files to the server's default locations.
Choose this option if the virtual machines files are already in the location from which they are to run.

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

### -SmartPagingFilePath
Specifies the new path to use for a smart paging file, if one is needed.

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

### -SnapshotFilePath
Specifies the path for any snapshot files associated with the virtual machine.

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

### -VhdDestinationPath
Specifies the folder to which the virtual machine's VHD files are to be copied.

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

### -VirtualMachinePath
Specifies the path where the virtual machine configuration files are to be stored.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.HyperV.PowerShell.VirtualMachine

## NOTES

## RELATED LINKS

