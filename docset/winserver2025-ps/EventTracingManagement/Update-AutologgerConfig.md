---
description: Modifies an existing AutoLogger session configuration.
external help file: MSFT_AutologgerConfig_v1.0.cdxml-help.xml
Module Name: EventTracingManagement
ms.date: 10/01/2021
online version: https://learn.microsoft.com/powershell/module/eventtracingmanagement/update-autologgerconfig?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-AutologgerConfig
---

# Update-AutologgerConfig

## SYNOPSIS
Modifies an existing AutoLogger session configuration.

## SYNTAX

### ByName (Default)
```
Update-AutologgerConfig [-Name] <String[]> [-BufferSize <UInt32>] [-ClockType <ClockType>]
 [-DisableRealtimePersistence <UInt32>] [-LocalFilePath <String>] [-FileMax <UInt32>] [-FlushTimer <UInt32>]
 [-Guid <String>] [-LogFileMode <UInt32>] [-MaximumFileSize <UInt32>] [-MaximumBuffers <UInt32>]
 [-MinimumBuffers <UInt32>] [-Start <UInt32>] [-InitStatus <UInt32>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Update-AutologgerConfig -InputObject <CimInstance[]> [-BufferSize <UInt32>] [-ClockType <ClockType>]
 [-DisableRealtimePersistence <UInt32>] [-LocalFilePath <String>] [-FileMax <UInt32>] [-FlushTimer <UInt32>]
 [-Guid <String>] [-LogFileMode <UInt32>] [-MaximumFileSize <UInt32>] [-MaximumBuffers <UInt32>]
 [-MinimumBuffers <UInt32>] [-Start <UInt32>] [-InitStatus <UInt32>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Update-AutologgerConfig** cmdlet modifies an existing AutoLogger session configuration.

## EXAMPLES

### Example 1: Modify a configuration
```
PS C:\> Update-AutologgerConfig -Name "WFP-IPsec Trace" -MaximumBuffers 8 -ClockType Cycle
```

This command modifies the AutoLogger configuration named WFP-IPsec Trace.

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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -BufferSize
Specifies the Event Tracing for Windows (ETW) trace session buffer size in KB.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
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

### -DisableRealtimePersistence
Specifies whether to not persist real-time events that were not delivered before the time the computer was shutdown.
Persisted events are delivered to the consumer the next time the consumer connects to the session.
To disable real time persistence, specify a value of one.
To persist events, specify a value of zero.
The default is zero.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
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
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -FlushTimer
Specifies the timeout value for ETW trace session to flush capture buffer.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -Guid
Specifies an AutoLogger session configuration ID.
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

### -InitStatus
Specifies the initial status of the AutoLogger configuration.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LocalFilePath
Specifies the full path for an ETW log file.

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
Specify one or more log modes, such as **EVENT_TRACE_REAL_TIME_MODE** 0x100.
Each mode is a bit field.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumBuffers
Specifies the maximum number of buffers for an ETW trace session.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumFileSize
Specifies the maximum size, in MB, of a log file before a new one is created.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumBuffers
Specifies the minimum number of buffers for an ETW trace session.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the AutoLogger session.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Indicates that this cmdlet returns an object that represents the item on which it operates.
By default, this cmdlet does not generate any output.

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

### -Start
By default, the AutoLogger session is configured to start at boot time.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
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
Default value: 0
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#ROOT\Microsoft\Windows\EventTracingManagement\MSFT_AutologgerConfig

## NOTES

## RELATED LINKS

[Configuring and Starting an AutoLogger Session](https://msdn.microsoft.com/library/windows/desktop/aa363687.aspx)

[Logging Mode Constants](https://msdn.microsoft.com/library/windows/desktop/aa364080.aspx)

[WNODE_HEADER structure](https://msdn.microsoft.com/library/windows/desktop/aa364160.aspx)

[Get-AutologgerConfig](./Get-AutologgerConfig.md)

[New-AutologgerConfig](./New-AutologgerConfig.md)

[Remove-AutologgerConfig](./Remove-AutologgerConfig.md)
