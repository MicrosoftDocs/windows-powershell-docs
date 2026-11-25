---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
Module Name: BootEventCollector
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/booteventcollector/start-sbecsimplelogsession?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-SbecSimpleLogSession
---

# Start-SbecSimpleLogSession

## SYNOPSIS
Starts a log session with the forwarding of events to the Collector.

## SYNTAX

```
Start-SbecSimpleLogSession [-Name] <String> [[-SessionGuid] <Guid>] [[-ProviderName] <String[]>]
 [[-ProviderGuid] <Guid[]>] [[-Level] <SeverityLevel>] [[-ClockType] <ClientContext>] [[-BufferSize] <UInt32>]
 [[-MinimumBufferCount] <UInt32>] [[-MaximumBufferCount] <UInt32>] [[-FlushSeconds] <UInt32>]
 [[-LogFileMode] <LoggingMode>] [[-KernelEnableFlags] <EventTraceFlag>] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Start-SbecSimpleLogSession** cmdlet starts a log session in boot event mode with a simpler subset of parameters.

To start a log session with more parameters, use Start-SbecLogSession.

## EXAMPLES


## PARAMETERS

### -BufferSize
Specifies the buffer size for the session, in kilobytes.
This is the size of one buffer, with the count of these buffers set by the *MinimumBufferCount* and *MaximumBufferCount* parameters.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClockType
Specifies the type of clock used for the events collected by this session: The acceptable values for this parameter are:

- Default.
- QueryPerformanceCounter.
  The high-resolution (period of 100 nanoseconds) clock that is typically used for performance measurement.
- SystemTime.
  The lower-resolution system time similar to FILETIME (period of 10 milliseconds).
  This value is most typical for the data collection through SBEC.
- CpuCycleCounter.
  The highest-resolution, with the frequency of the CPU, but may be unreliable depending on the CPU model and the thermal and power modes.

```yaml
Type: ClientContext
Parameter Sets: (All)
Aliases:
Accepted values: Default, QueryPerformanceCounter, SystemTime, CpuCycleCounter

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FlushSeconds
Specifies the timeout, in seconds, for the session buffers to automatically flush.
You can disable the flushing of buffers on timeout by setting this parameter to 0, then the buffers will be written only when full or on an explicit flush.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: FlushTimer

Required: False
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KernelEnableFlags
Specifies flags for the NT Kernel Logger that enable the kernel events.
For the setup and boot monitoring, the only reasonable flag is Process.
This enumeration type is defined in $PsHome\Modules\BootEventCollector\SbecTraceHelpers.psm1.
The acceptable values for this parameter are:

- None
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
Type: EventTraceFlag
Parameter Sets: (All)
Aliases:
Accepted values: None, Process, Thread, ImageLoad, ProcessCounters, ContextSwitch, Dpc, Interrupt, SystemCall, DiskIO, DiskFileIO, DiskIOInit, Dispatcher, MemoryPageFaults, MemoryHardFaults, VirtualAlloc, NetworkTCPIP, Registry, Alpc, SplitIO, Driver, FileIO, FileIOInit, Profile

Required: False
Position: 11
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Level
Specifies the highest detail level value to enable for providers.
This enumeration type is defined in $PsHome\Modules\BootEventCollector\SbecTraceHelpers.psm1.
The acceptable values for this parameter are:

- Undefined
- Fatal
- Error
- Warning
- Information
- Verbose
- All

```yaml
Type: SeverityLevel
Parameter Sets: (All)
Aliases:
Accepted values: Undefined, Fatal, Error, Warning, Information, Verbose, All

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogFileMode
Specifies the new flags for the log file mode.
The EnableKd and DisableKd values parameters are applied on top of these flags.
This enumeration type is defined in $PsHome\Modules\BootEventCollector\SbecTraceHelpers.psm1.
The cmdlet automatically adds the RealTime and KdFilter values to this parameter.
Other frequently used flags for this context are:

- Secure.
Restricts who can log events to the session to those with TRACELOG_LOG_EVENT permission.
- UsePagedMemory.
Use the paged memory for the buffers.
- NoPerProcessorBuffering.
Write the events from all processors to the same buffer.
This preserves the order of the events, and is recommended for sending the events to the event collector.

The acceptable values for this parameter are:

- None
- FileNone
- FileSequential
- FileCircular
- FileAppend
- FileNewFile
- Reserved0x00000010
- FilePreallocate
- Nonstoppable
- Secure
- RealTime
- DelayOpenFile
- Buffering
- PrivateLogger
- AddHeader
- UseKilobytesForSize
- UseGlobalSequence
- Relog
- PrivateInProc
- BufferInterface
- KdFilter
- RealtimeRelog
- LostEventsDebug
- StopOnHybridShutdown
- PersistOnHybridShutdown
- UsePagedMemory
- SystemLogger
- Compressed
- IndependentSession
- NoPerProcessorBuffering
- Blocking
- Reserved0x40000000
- AddToTriageDump
- Fatal
- Error
- Warning
- Information
- Verbose
- All

```yaml
Type: LoggingMode
Parameter Sets: (All)
Aliases:
Accepted values: None, FileNone, FileSequential, FileCircular, FileAppend, FileNewFile, Reserved0x00000010, FilePreallocate, Nonstoppable, Secure, RealTime, DelayOpenFile, Buffering, PrivateLogger, AddHeader, UseKilobytesForSize, UseGlobalSequence, UseLocalSequence, Relog, PrivateInProc, BufferInterface, KdFilter, RealtimeRelog, LostEventsDebug, StopOnHybridShutdown, PersistOnHybridShutdown, UsePagedMemory, SystemLogger, Compressed, IndependentSession, NoPerProcessorBuffering, Blocking, Reserved0x40000000, AddToTriageDump

Required: False
Position: 10
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
Position: 8
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
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the session to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -ProviderGuid
Specifies the provider GUIDs to subscribe this session to.
The providers are configured to include all events up to the level specified by the *Level* parameter.

```yaml
Type: Guid[]
Parameter Sets: (All)
Aliases: pg

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProviderName
Specifies the provider names to subscribe this session to.
The providers are configured to include all events up to the level specified by the *Level* parameter.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: pn

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SessionGuid
Specifies the GUID for the session.
By default the GUID gets generated and assigned automatically.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None.

## OUTPUTS

### SbecEtwTrace.TraceSessionInfo
The **SbecEtwTrace.TraceSessionInfo** class is defined in $PsHome\Modules\BootEventCollector\SbecTraceHelpers.psm1.

## NOTES

## RELATED LINKS

[Get-SbecLogSession](./Get-SbecLogSession.md)

[Save-SbecLogSession](./Save-SbecLogSession.md)

[Set-SbecLogSession](./Set-SbecLogSession.md)

[Start-SbecLogSession](./Start-SbecLogSession.md)

[Start-SbecNtKernelLogSession](./Start-SbecNtKernelLogSession.md)

[Stop-SbecLogSession](./Stop-SbecLogSession.md)

