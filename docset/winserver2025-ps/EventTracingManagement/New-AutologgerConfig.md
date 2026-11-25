---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_AutologgerConfig_v1.0.cdxml-help.xml
Module Name: EventTracingManagement
ms.date: 01/05/2017
online version: https://learn.microsoft.com/powershell/module/eventtracingmanagement/new-autologgerconfig?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-AutologgerConfig
---

# New-AutologgerConfig

## SYNOPSIS
Creates an Autologger session configuration in the registry.

## SYNTAX

```
New-AutologgerConfig -Name <String> [-BufferSize <UInt32>] [-ClockType <ClockType>]
 [-DisableRealtimePersistence <UInt32>] [-FileCount <UInt32>] [-LocalFilePath <String>] [-FileMax <UInt32>]
 [-FlushTimer <UInt32>] [-Guid <String>] [-LogFileMode <UInt32>] [-MaximumFileSize <UInt32>]
 [-MaximumBuffers <UInt32>] [-MinimumBuffers <UInt32>] [-Start <Enabled>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-AutologgerConfig** cmdlet creates an Autologger session configuration in the registry.

## EXAMPLES

### Example 1: Create a configuration
```
PS C:\> New-AutoLoggerConfig -Name "WFP-IPsec Trace"
```

This command creates an AutoLogger configuration named WFP-IPsec Trace.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -BufferSize
Specifies the ETW session buffer size, in kilobytes.

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
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClockType
Specifies the type of timestamp that will be used for each event logged to this ETW session.

This is an advanced session configuration option, and it is not recommended that this parameter be set.

For more information, see the description of the **ClientContext** field in [WNODE_HEADER structure](https://msdn.microsoft.com/en-us/library/windows/desktop/aa364160.aspx) for a description of clock types.

```yaml
Type: ClockType
Parameter Sets: (All)
Aliases:
Accepted values: Performance, System, Cycle

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

### -DisableRealtimePersistence
Controls whether undelivered events from a real time session will be delivered or discarded when Windows next starts up.

For more information, see [Configuring and Starting an AutoLogger Session](https://msdn.microsoft.com/en-us/library/windows/desktop/aa363687.aspx) in MSDN.

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

### -FileCount
Specifies the file count value.

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

### -FileMax
Specifies the maximum number of log files an AutoLogger session can create.

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

### -Guid
Specifies a unique GUID for this AutoLogger session.

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
Specifies the name of the new AutoLogger session.
This will be used as the name of the ETW session that gets created by this AutoLogger.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Start
If set to Enabled, an ETW session for this AutoLogger will be created when Windows starts.

```yaml
Type: Enabled
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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

[Configuring and Starting an AutoLogger Session](https://msdn.microsoft.com/library/windows/desktop/aa363687.aspx)

[Logging Mode Constants](https://msdn.microsoft.com/library/windows/desktop/aa364080.aspx)

[WNODE_HEADER structure](https://msdn.microsoft.com/library/windows/desktop/aa364160.aspx)

[Get-AutologgerConfig](./Get-AutologgerConfig.md)

[Remove-AutologgerConfig](./Remove-AutologgerConfig.md)

[Update-AutologgerConfig](./Update-AutologgerConfig.md)

