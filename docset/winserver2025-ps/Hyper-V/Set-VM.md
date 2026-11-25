---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vm?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VM
---

# Set-VM

## SYNOPSIS
Configures a virtual machine.

## SYNTAX

### Name (Default)
```
Set-VM [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-Name] <String[]> [-GuestControlledCacheTypes <Boolean>] [-LowMemoryMappedIoSpace <UInt32>]
 [-HighMemoryMappedIoSpace <UInt64>] [-ProcessorCount <Int64>] [-DynamicMemory] [-StaticMemory]
 [-MemoryMinimumBytes <Int64>] [-MemoryMaximumBytes <Int64>] [-MemoryStartupBytes <Int64>]
 [-AutomaticStartAction <StartAction>] [-AutomaticStopAction <StopAction>] [-AutomaticStartDelay <Int32>]
 [-AutomaticCriticalErrorAction <CriticalErrorAction>] [-AutomaticCriticalErrorActionTimeout <Int32>]
 [-AutomaticCheckpointsEnabled <Boolean>]
 [-LockOnDisconnect <OnOffState>] [-Notes <String>] [-NewVMName <String>] [-SnapshotFileLocation <String>]
 [-SmartPagingFilePath <String>] [-CheckpointType <CheckpointType>] [-Passthru] [-AllowUnverifiedPaths]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Set-VM [-VM] <VirtualMachine[]> [-GuestControlledCacheTypes <Boolean>] [-LowMemoryMappedIoSpace <UInt32>]
 [-HighMemoryMappedIoSpace <UInt64>] [-ProcessorCount <Int64>] [-DynamicMemory] [-StaticMemory]
 [-MemoryMinimumBytes <Int64>] [-MemoryMaximumBytes <Int64>] [-MemoryStartupBytes <Int64>]
 [-AutomaticStartAction <StartAction>] [-AutomaticStopAction <StopAction>] [-AutomaticStartDelay <Int32>]
 [-AutomaticCriticalErrorAction <CriticalErrorAction>] [-AutomaticCriticalErrorActionTimeout <Int32>]
 [-AutomaticCheckpointsEnabled <Boolean>]
 [-LockOnDisconnect <OnOffState>] [-Notes <String>] [-NewVMName <String>] [-SnapshotFileLocation <String>]
 [-SmartPagingFilePath <String>] [-CheckpointType <CheckpointType>] [-Passthru] [-AllowUnverifiedPaths]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VM** cmdlet configures a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\> Set-VM -Name TestVM -AutomaticStopAction Shutdown
```

Configures virtual machine TestVM to shut down when the Hyper-V host shuts down.

### Example 2
```
PS C:\> Stop-VM -Name TestVM -Passthru | Set-VM -ProcessorCount 2 -DynamicMemory -MemoryMaximumBytes 2GB -Passthru | Start-VM
```

Stops virtual machine TestVM, sets it to use dynamic memory, sets its maximum amount of memory to 2GB, sets it to use 2 virtual processors, and starts it.

## PARAMETERS

### -AllowUnverifiedPaths
Specifies that no error is to be thrown if the specified path is not verified as accessible by the cluster.
This parameter is applicable to clustered virtual machines.

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

### -AutomaticCheckpointsEnabled
Specifies whether automatic checkpoints are enabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutomaticCriticalErrorAction
Specifies the action to take when the VM encounters a critical error, and exceeds the timeout duration specified by the **AutomaticCriticalErrorActionTimeout** cmdlet.
The acceptable values for this parameter are: Pause and None.

```yaml
Type: CriticalErrorAction
Parameter Sets: (All)
Aliases:
Accepted values: None, Pause

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutomaticCriticalErrorActionTimeout
Specifies the amount of time, in minutes, to wait in critical pause before powering off the virtual machine.

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

### -AutomaticStartAction
Specifies the action the virtual machine is to take upon start.
Allowed values are **Nothing**, **StartIfRunning**, and **Start**.

```yaml
Type: StartAction
Parameter Sets: (All)
Aliases:
Accepted values: Nothing, StartIfRunning, Start

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutomaticStartDelay
Specifies the number of seconds by which the virtual machine's start should be delayed.

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

### -AutomaticStopAction
Specifies the action the virtual machine is to take when the virtual machine host shuts down.
Allowed values are **TurnOff**, **Save**, and **ShutDown**.

```yaml
Type: StopAction
Parameter Sets: (All)
Aliases:
Accepted values: TurnOff, Save, ShutDown

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CheckpointType
Allows you to configure the type of checkpoints created by Hyper-V.
The acceptable values for this parameter are:

- Disabled.
Block creation of checkpoints.
- Standard.
Create standard checkpoints.
- Production.
Create production checkpoints if supported by guest operating system.
Otherwise, create standard checkpoints.
- ProductionOnly.
Create production checkpoints if supported by guest operating system.
Otherwise, the operation fails.

```yaml
Type: CheckpointType
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Production, ProductionOnly, Standard

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
Specifies one or more Hyper-V hosts on which the virtual machine is to be configured.
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

### -DynamicMemory
Specifies that the virtual machine is to be configured to use dynamic memory.

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

### -GuestControlledCacheTypes
Specifies whether this virtual machine uses guest controlled cache types.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HighMemoryMappedIoSpace


```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LockOnDisconnect
Specifies whether virtual machine connection in basic mode locks the console after a user disconnects.

```yaml
Type: OnOffState
Parameter Sets: (All)
Aliases:
Accepted values: On, Off

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LowMemoryMappedIoSpace


```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MemoryMaximumBytes
Specifies the maximum amount of memory that the virtual machine is to be allocated.
(Applies only to virtual machines using dynamic memory.)

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MemoryMinimumBytes
Specifies the minimum amount of memory that the virtual machine is to be allocated.
(Applies only to virtual machines using dynamic memory.)

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MemoryStartupBytes
Specifies the amount of memory that the virtual machine is to be allocated upon startup.
(If the virtual machine does not use dynamic memory, then this is the static amount of memory to be allocated.)

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual machine to be configured.

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

### -NewVMName
Specifies the name to which the virtual machine is to be renamed.

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

### -Notes
Specifies notes to be associated with the virtual machine.

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

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the virtual machine to be configured.

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

### -ProcessorCount
Specifies the number of virtual processors for the virtual machine.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SmartPagingFilePath
Specifies the folder in which the Smart Paging file is to be stored.

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

### -SnapshotFileLocation
Specifies the folder in which the virtual machine is to store its snapshot files.

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

### -StaticMemory
This cmdlet configures the virtual machine to use static memory.
Specify the amount of static memory to allocate by using the **MemoryStartupBytes** parameter.

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

### -VM
Specifies the virtual machine to be configured.

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

