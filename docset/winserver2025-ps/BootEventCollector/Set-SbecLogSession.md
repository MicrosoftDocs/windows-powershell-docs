---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
Module Name: BootEventCollector
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/booteventcollector/set-sbeclogsession?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-SbecLogSession
---

# Set-SbecLogSession

## SYNOPSIS
Updates the settings for a log session.

## SYNTAX

### Object
```
Set-SbecLogSession -Session <TraceSessionInfo[]> [-Path <Object>] [-ClockType <Object>] [-BufferSize <Object>]
 [-MinimumBufferCount <UInt32>] [-MaximumBufferCount <UInt32>] [-MaximumFileSize <Object>]
 [-FlushSeconds <UInt32>] [-LogFileMode <Object>] [-KernelEnableFlags <Object>] [-EnableKd] [-DisableKd]
 [-SimulateError <Int32>] [<CommonParameters>]
```

### Name
```
Set-SbecLogSession -Name <String[]> [-Path <Object>] [-ClockType <Object>] [-BufferSize <Object>]
 [-MinimumBufferCount <UInt32>] [-MaximumBufferCount <UInt32>] [-MaximumFileSize <Object>]
 [-FlushSeconds <UInt32>] [-LogFileMode <Object>] [-KernelEnableFlags <Object>] [-EnableKd] [-DisableKd]
 [-SimulateError <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SbecLogSession** cmdlet updates the settings for a log session.

You can change the properties of an object before passing it as input to this cmdlet rather than passing changes as parameters.
In this case, make sure to set the properties directly in the object rather than in its Trace field (the modifications of Trace are silently ignored by PowerShell).

The cmdlet parameters that are unused or set to $Null are left unchanged.

You cannot update the session name.

The operating system may refuse to change some parameters or silently ignore the updates.

## EXAMPLES


## PARAMETERS

### -BufferSize
Specifies the buffer size for the session, in kilobytes.
This is the size of one buffer, with the count of these buffers set by the *MinimumBufferCount* and *MaximumBufferCount* parameters.

```yaml
Type: Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClockType
Specifies the type of clock used for the events collected by this session.
The acceptable values for this parameter are:

- QueryPerformanceCounter.
The high-resolution (period of 100 nanoseconds) clock that is typically used for performance measurement.
- SystemTime.
The lower-resolution system time similar to FILETIME (period of 10 milliseconds).
This value is most typical for the data collection through SBEC.
- CpuCycleCounter.
The highest-resolution, with the frequency of the CPU, but may be unreliable depending on the CPU model and the thermal and power modes.

```yaml
Type: Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableKd
Changes the LogFileMode flags to disable the forwarding through the kernel transport to the collector for the real-time log sessions.
The switches *EnableKd* and *DisableKd* are mutually exclusive.

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

### -EnableKd
Changes the LogFileMode flags to enable the forwarding through the kernel transport to the collector for the real-time log sessions.
The switches *EnableKd* and *DisableKd* are mutually exclusive.

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

### -FlushSeconds
Specifies the timeout in seconds for the session buffers to get automatically flushed.
You can disable the flushing of buffers on timeout by setting this parameter to 0, then the buffers will be written only when full or on an explicit flush.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: FlushTimer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KernelEnableFlags
Specifies flags for the NT Kernel Logger that enable the kernel events.
For the setup and boot monitoring, the only reasonable flag is Process.
This enumeration type is defined in $PsHome\Modules\BootEventCollector\SbecTraceHelpers.psm1.
The acceptable values for this parameter are:

- Process
- Thread
- ImageLoad
- ProcessCounters
- ContextSwitch
- Dpc
- Interrupt
- SystemCall
- DiskIO
- DiskFileIO
- DiskIOInit
- Dispatcher
- MemoryPageFaults
- MemoryHardFaults
- VirtualAlloc
- NetworkTCPIP
- Registry
- Alpc
- SplitIO
- Driver
- FileIO
- FileIOInit
- Profile

```yaml
Type: Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogFileMode
Specifies the new flags for the log file mode.
The parameters *EnableKd* and *DisableKd* are applied on top of these flags.
This enumeration type is defined in $PsHome\Modules\BootEventCollector\SbecTraceHelpers.psm1.
The most used bit values in it are:

- FileSequential.
Write events to a log file sequentially; stops when the file reaches its maximum size.
- FileCircular.
Write events to a log file.
After the file reaches the maximum size, replace the oldest events with incoming events.
- FileAppend.
Append events to an existing sequential log file.
- FileNewFile.
Automatically switch to a new log file when the file reaches the maximum size.
- FilePreallocate.
Reserve the MaximumFileSize of disk space for the log files in advance.
- Secure.
Restrict who can log events to the session to those with TRACELOG_LOG_EVENT permission.
- RealTime.
Deliver the events to consumers in real-time instead of writing them to a file.
This mode is required for sending the events to the event collector.
- KdFilter.
Forward the events though the kernel channel to the event collector or to the debugger.
- UsePagedMemory.
Use the paged memory for the buffers.
- NoPerProcessorBuffering.
Write the events from all processors to the same buffer.
This preserves the order of the events, and is recommended for sending the events to the event collector.

```yaml
Type: Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumBufferCount
Specifies the maximum number of buffers to allocate for this session.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: MaximumBuffers, maxbuf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumFileSize
Specifies the maximum file size after which the session may switch to the next file, in megabytes.
Use 0 for no limit.

```yaml
Type: Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumBufferCount
Specifies the minimum number of buffers to allocate for this session.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: MinimumBuffers, minbuf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the session to create.

```yaml
Type: String[]
Parameter Sets: Name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the ETL file where the session will write its log.
The session must have the file mode enabled to write to a file; a session in the real-time mode ignores the file.

```yaml
Type: Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Session
Specifies the GUID for the session.

```yaml
Type: TraceSessionInfo[]
Parameter Sets: Object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SimulateError
Simulates a Windows error in session creation, and causes the function to throw an error.
You can specify this parameter to test error handling.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### SbecEtwTrace.TraceSessionInfo
The class is defined in $PsHome\Modules\BootEventCollector\SbecTraceHelpers.psm1.

## OUTPUTS

### None.

## NOTES

## RELATED LINKS

[Get-SbecLogSession](./Get-SbecLogSession.md)

[Save-SbecLogSession](./Save-SbecLogSession.md)

[Start-SbecLogSession](./Start-SbecLogSession.md)

[Start-SbecNtKernelLogSession](./Start-SbecNtKernelLogSession.md)

[Start-SbecSimpleLogSession](./Start-SbecSimpleLogSession.md)

[Stop-SbecLogSession](./Stop-SbecLogSession.md)

