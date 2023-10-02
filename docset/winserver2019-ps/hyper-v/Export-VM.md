---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/export-vm?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-VM
---

# Export-VM

## SYNOPSIS
Exports a virtual machine to disk.

## SYNTAX

### Name (Default)
```
Export-VM [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-Name] <String[]> [-Path] <String> [-AsJob] [-Passthru] [-CaptureLiveState <CaptureLiveState>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### VMObject
```
Export-VM [-VM] <VirtualMachine[]> [-Path] <String> [-AsJob] [-Passthru] [-CaptureLiveState <CaptureLiveState>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Export-VM** cmdlet exports a virtual machine to disk.
This cmdlet creates a folder at a specified location having three subfolders: Snapshots, Virtual Hard Disks, and Virtual Machines.
Each of these folders contains the associated files. The Snapshots folder contains the associated Snapshots, and the Virtual Hard Disk folder contains the specified virtual machine's virtual disks.
The Virtual Machines folder contains the configuration XML of the specified virtual machine.

## EXAMPLES

### Example 1
```
PS C:\> Export-VM -Name Test -Path D:\
```

Exports virtual machine Test to the root of the D drive.

### Example 2
```
PS C:\> Get-VM | Export-VM -Path D:\
```

Exports all virtual machines to the root of the D drive.
Each virtual machine will be exported to its own folder.

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

### -CaptureLiveState
Specifies how Hyper-V captures the running virtual machine memory state.
The acceptable values for this parameter are:

- CaptureSavedState.
Include memory state. 
- CaptureDataConsistentState.
Use Production Checkpoint technology. 
- CaptureCrashConsistentState.
Do nothing to handle virtual machine state.

```yaml
Type: CaptureLiveState
Parameter Sets: (All)
Aliases: 
Accepted values: CaptureCrashConsistentState, CaptureSavedState, CaptureDataConsistentState

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
Parameter Sets: Name
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual machine is to be exported.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: Name
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
Parameter Sets: Name
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual machine to be exported.

```yaml
Type: String[]
Parameter Sets: Name
Aliases: VMName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.HyperV.PowerShell.VirtualMachine** object is to be passed through to the pipeline representing the virtual machine to be exported.

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

### -Path
Specifies the path to the folder into which the virtual machine is to be exported.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine to be exported.

```yaml
Type: VirtualMachine[]
Parameter Sets: VMObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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
Default

### Microsoft.HyperV.PowerShell.VirtualMachine
If **-PassThru** is specified.

## NOTES

## RELATED LINKS

