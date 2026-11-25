---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/import-vm?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-VM
---

# Import-VM

## SYNOPSIS
Imports a virtual machine from a file.

## SYNTAX

### Register (Default)
```
Import-VM [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-Path] <String> [-Register] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Copy
```
Import-VM [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-Path] <String> [[-VhdDestinationPath] <String>] [-Copy] [-VirtualMachinePath <String>]
 [-SnapshotFilePath <String>] [-SmartPagingFilePath <String>] [-VhdSourcePath <String>] [-GenerateNewId]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
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
PS C:\> Import-VM -Path 'C:\<vm export path>\2B91FEB3-F1E0-4FFF-B8BE-29CED892A95A.vmcx'
```

Imports the virtual machine from its configuration file.
The virtual machine is registered in-place, so its files are not copied.

### Example 2
```
PS C:\> Import-VM -Path 'C:\<vm export path>\2B91FEB3-F1E0-4FFF-B8BE-29CED892A95A.vmcx' -Copy -GenerateNewId
```

Imports the virtual machine by copying its files to the default virtual machine and virtual hard drive storage locations of the Hyper-V host.
The imported virtual machine will be given a new unique identifier, not the one in the configuration file.
This is useful when you want to import multiple copies of a virtual machine, since each virtual machine must have a unique identifier.

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
Parameter Sets: Register, Copy
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
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: Register, Copy
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

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: Register, Copy
Aliases:

Required: False
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
Aliases: CheckpointFileLocation, SnapshotFileLocation

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.HyperV.PowerShell.VirtualMachine

## NOTES

## RELATED LINKS

