---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: EventTracingManagement-help.xml
Module Name: EventTracingManagement
ms.date: 01/05/2017
online version: https://learn.microsoft.com/powershell/module/eventtracingmanagement/start-etwtracesession?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-EtwTraceSession
---

# Start-EtwTraceSession

## SYNOPSIS
Starts an ETW session with the specified name and settings.

## SYNTAX

```
Start-EtwTraceSession [-Name] <String> [-LogFileMode <UInt32>] [-LocalFilePath <String>]
 [-MaximumFileSize <UInt32>] [-BufferSize <UInt32>] [-MinimumBuffers <UInt32>] [-MaximumBuffers <UInt32>]
 [-FlushTimer <UInt32>] [-ClockType <String>] [-FileMode <String>] [-Compress] [-RealTime] [-NonPaged]
 [-CimSession <CimSession>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-EtwTraceSession** cmdlet starts an ETW session with the specified name and settings.

## EXAMPLES


## PARAMETERS

### -BufferSize
Specifies the Event Tracing for Windows (ETW) session buffer size, in kilobytes.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClockType
Specifies the type of timestamp that will be used for each event logged to this ETW session.

This is an advanced session configuration option, and it is not recommended that this parameter be set.

For more information, see the description of the **ClientContext** field in the topic [WNODE_HEADER structure](https://msdn.microsoft.com/en-us/library/windows/desktop/aa364160.aspx) for a description of the different clock types available.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Performance, System, Cycle

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Compress
Controls whether ETW should compress the saved buffers as they are filled.
Enabling this parameter sets the **EVENT_TRACE_COMPRESSED_MODE** bit in the *LogFileMode* parameter.

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

### -FileMode
Specifies how events received by the session should be saved.
*FileMode* provides named values for common logging mode constants, and setting it will affect the value of *LogFileMode* that is passed to ETW when the session is created.

If you specify this parameter do not specify any file or buffering mode bits in the *LogFileMode* parameter.

For more information about available modes, see [Logging Mode Constants](https://msdn.microsoft.com/en-us/library/windows/desktop/aa364080.aspx) in MSDN.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: File, Buffering, Sequential, Circular

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FlushTimer
When set, all active buffers in the session will be flushed at this interval, in seconds.

This is an advanced session configuration option, and it is not recommended that this parameter be set.

If it is not set, the ETW will select an appropriate default based on the *LogFileMode*.

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

### -LocalFilePath
Specifies the full path to the file the ETW session should write to.
For non-buffering mode sessions only.

When creating a new-file file mode session, the file path must contain a %d in the file name.

Do not use this parameter if the session is configured as a buffering mode session.
Use **Save-EtwTraceSession** to save a buffering mode session to disk instead.

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

### -LogFileMode
Specifies the ETW session logging mode.
The value is a bitmask of the ETW logging mode constants.

For more information, see [Logging Mode Constants](https://msdn.microsoft.com/en-us/library/windows/desktop/aa364080.aspx) in MSDN.

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

### -MaximumBuffers
Specifies the maximum number of buffers the ETW session should use.

The ETW session will use a maximum of (*BufferSize* * *MaximumBuffers*) kilobytes of memory.
Depending on the specified *LogFileMode*, this may be pageable or non-paged memory.

If the session is losing events because the buffers cannot be flushed quick enough to keep up with the incoming event rate, try increasing this value.

Configuring a session to use too many buffers may affect system performance.

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

### -MaximumFileSize
Specifies the maximum file size for the output .etl file to grow to, in megabytes.

The parameter must be set for a circular, new-file, or sequential file mode ETW session.

For circular sessions, once the file reaches this size the oldest buffers will be overwritten by the new buffers.

For new-file sessions, once the file reaches this size a new file will be created and all new events will be written to that file.

For sequential file sessions, once the file reaches this size the session will stop.

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

### -MinimumBuffers
Specifies the minimum number of buffers the ETW session should use.

The ETW session will use a minimum of (*BufferSize* * *MinimumBuffers*) kilobytes of memory.
Depending on the specified *LogFileMode*, this may be pageable or non-paged memory.

If the session is losing events because the buffers cannot be flushed quick enough to keep up with the incoming event rate, try increasing this value.

Configuring a session to use too many buffers may affect system performance.

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

### -Name
Specifies the name of the ETW trace session.

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

### -NonPaged
Controls whether ETW should use memory from the non-paged pool for the session buffers.
Enabling this parameter clears the **EVENT_TRACE_USE_PAGED_MEMORY** bit in the *LogFileMode* parameter.

Using memory from the non-paged pool for the session buffers is only required if any of the events that will be sent to the session are logged from the kernel or a driver at high a dispatch level.
This parameter should not be set otherwise.

Allocating too much memory from the non-paged pool can seriously degrade system performance.

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

### -RealTime
Controls whether ETW should allow real-time consumers to connect to the session.
Enabling this parameter sets the **EVENT_TRACE_REAL_TIME_MODE** bit in the *LogFileMode* parameter.

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

## NOTES

## RELATED LINKS

[Get-EtwTraceSession](./Get-EtwTraceSession.md)

[New-EtwTraceSession](./New-EtwTraceSession.md)

[Save-EtwTraceSession](./Save-EtwTraceSession.md)

[Send-EtwTraceSession](./Send-EtwTraceSession.md)

[Stop-EtwTraceSession](./Stop-EtwTraceSession.md)

[Update-EtwTraceSession](./Update-EtwTraceSession.md)

