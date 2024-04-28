---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_EtwTraceProvider_v1.0.cdxml-help.xml
Module Name: EventTracingManagement
ms.date: 01/05/2017
online version: https://learn.microsoft.com/powershell/module/eventtracingmanagement/add-etwtraceprovider?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-EtwTraceProvider
---

# Add-EtwTraceProvider

## SYNOPSIS
Adds an ETW trace provider to an ETW trace session or AutoLogger session configuration.

## SYNTAX

### BySession
```
Add-EtwTraceProvider [-Guid] <String> [-Level <Byte>] [-MatchAnyKeyword <UInt64>] [-MatchAllKeyword <UInt64>]
 [-Property <UInt32>] -SessionName <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByAutologger
```
Add-EtwTraceProvider [-Guid] <String> -AutologgerName <String> [-Level <Byte>] [-MatchAnyKeyword <UInt64>]
 [-MatchAllKeyword <UInt64>] [-Property <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-EtwTraceProvider** cmdlet adds an Event Tracing for Windows (ETW) trace provider to a specified ETW trace session or AutoLogger session configuration with the specified parameters.

## EXAMPLES

### Example 1: Add an ETW trace provider to an AutoLogger configuration
```
PS C:\> Add-EtwTraceProvider -Guid "{5EEFEBDB-E90C-423A-8ABF-0241E7C5B87D}" -AutologgerName "WFP-IPsec Trace"
SessionName     :
AutologgerName  : WFP-IPsec Trace
Guid            : {5EEFEBDB-E90C-423A-8ABF-0241E7C5B87D}
Level           : 0
MatchAnyKeyword : 0x0
MatchAllKeyword : 0x0
Property        : 0
```

This command adds the ETW trace provider that has the specified GUID to an AutoLogger configuration named WFP-IPsec Trace.

### Example 2: Add an ETW trace provider to an ETW session
```
PS C:\> Add-EtwTraceProvider -Guid "{5EEFEBDB-E90C-423A-8ABF-0241E7C5B87D}" -SessionName "VMM"
SessionName     : VMM
AutologgerName  :
Guid            : {5EEFEBDB-E90C-423A-8ABF-0241E7C5B87D}
Level           : 0
MatchAnyKeyword : 0x0
MatchAllKeyword : 0x0
Property        : 0
```

This command adds the ETW trace provider that has the specified GUID to an session named VMM.

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

### -AutologgerName
Specifies the name of the target AutoLogger session.

```yaml
Type: String
Parameter Sets: ByAutologger
Aliases:

Required: True
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

### -Guid
Specifies the provider ID.

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

### -Level
Specifies the maximum event level for which to enable for collection.

For more information, see [EnableTraceEx2 function](https://msdn.microsoft.com/en-us/library/windows/desktop/dd392305.aspx) on MSDN.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MatchAllKeyword
Specifies a bitmask of keywords an event must match in order to be logged to the session.

An event must match every keyword set by this parameter.
Most of the time, the *MatchAnyKeyword* parameter is more suitable.

For more information, see [EnableTraceEx2 function](https://msdn.microsoft.com/en-us/library/windows/desktop/dd392305.aspx) on MSDN.

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

### -MatchAnyKeyword
Specifies a bitmask of keywords an event must match in order to be logged to the session.

An event must match at least one keyword set by this parameter.

For more information, see [EnableTraceEx2 function](https://msdn.microsoft.com/en-us/library/windows/desktop/dd392305.aspx) on MSDN.

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

### -Property
Specifies the Enable property to use for events logged from this provider to the session.

For more information, see [Configuring and Starting an AutoLogger Session](https://msdn.microsoft.com/en-us/library/windows/desktop/aa363687.aspx).

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

### -SessionName
Specifies the name of the target ETW session.

```yaml
Type: String
Parameter Sets: BySession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of zero is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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

[Configuring and Starting an Event Tracing Session](https://msdn.microsoft.com/library/windows/desktop/aa363688.aspx)

[Get-EtwTraceProvider](./Get-EtwTraceProvider.md)

[Remove-EtwTraceProvider](./Remove-EtwTraceProvider.md)

[Set-EtwTraceProvider](./Set-EtwTraceProvider.md)

