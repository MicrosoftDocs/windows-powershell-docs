---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
Module Name: BootEventCollector
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/booteventcollector/start-sbecntkernellogsession?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-SbecNtKernelLogSession
---

# Start-SbecNtKernelLogSession

## SYNOPSIS
Starts an NT Kernel Logger log session with forwarding of events to the Collector.

## SYNTAX

```
Start-SbecNtKernelLogSession [[-ClockType] <ClientContext>] [[-BufferSize] <UInt32>]
 [[-MinimumBufferCount] <UInt32>] [[-MaximumBufferCount] <UInt32>] [[-FlushSeconds] <UInt32>]
 [[-KernelEnableFlags] <EventTraceFlag>] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Start-SbecNtKernelLogSession** cmdlet starts a real-time NT Kernel Logger trace session with forwarding of the events to the Collector.
The name of the session is fixed as NT Kernel Logger and the GUID is fixed as {9e814aad-3204-11d2-9a82-006008a86939}.

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
Position: 1
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
Position: 0
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
Position: 4
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
Type: EventTraceFlag
Parameter Sets: (All)
Aliases:
Accepted values: None, Process, Thread, ImageLoad, ProcessCounters, ContextSwitch, Dpc, Interrupt, SystemCall, DiskIO, DiskFileIO, DiskIOInit, Dispatcher, MemoryPageFaults, MemoryHardFaults, VirtualAlloc, NetworkTCPIP, Registry, Alpc, SplitIO, Driver, FileIO, FileIOInit, Profile

Required: False
Position: 5
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
Position: 3
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
Position: 2
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

[Start-SbecLogSession](./Start-SbecLogSession.md)

[Start-SbecSimpleLogSession](./Start-SbecSimpleLogSession.md)

[Stop-SbecLogSession](./Stop-SbecLogSession.md)

[Set-SbecLogSession](./Set-SbecLogSession.md)

[Save-SbecLogSession](./Save-SbecLogSession.md)

