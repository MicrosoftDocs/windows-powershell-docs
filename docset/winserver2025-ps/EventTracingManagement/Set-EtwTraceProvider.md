---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_EtwTraceProvider_v1.0.cdxml-help.xml
Module Name: EventTracingManagement
ms.date: 01/05/2017
online version: https://learn.microsoft.com/powershell/module/eventtracingmanagement/set-etwtraceprovider?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-EtwTraceProvider
---

# Set-EtwTraceProvider

## SYNOPSIS
Modifies a provider's enablement settings in an ETW or AutoLogger session.

## SYNTAX

### ByAutologger (Default)
```
Set-EtwTraceProvider [[-Guid] <String[]>] [-AutologgerName <String[]>] [-Level <Byte>]
 [-MatchAnyKeyword <UInt64>] [-MatchAllKeyword <UInt64>] [-Property <UInt32>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BySession
```
Set-EtwTraceProvider [[-Guid] <String[]>] [-SessionName <String[]>] [-Level <Byte>] [-MatchAnyKeyword <UInt64>]
 [-MatchAllKeyword <UInt64>] [-Property <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-EtwTraceProvider -InputObject <CimInstance[]> [-Level <Byte>] [-MatchAnyKeyword <UInt64>]
 [-MatchAllKeyword <UInt64>] [-Property <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-EtwTraceProvider** cmdlet modifies a provider's enablement settings in an Event Tracing for Windows (ETW) or AutoLogger session.

## EXAMPLES

### Example 1: Modify an ETW trace provider
```
PS C:\> set-EtwTraceProvider -Guid "{106B464A-8043-46B1-8CB8-E92A0CD7A560}" -AutologgerName "WFP-IPsec Trace" -Level 2
SessionName     :
AutologgerName  : WFP-IPsec Trace
Guid            : {106B464A-8043-46B1-8CB8-E92A0CD7A560}
Level           : 2
MatchAnyKeyword : 0xFFFFFFFF
MatchAllKeyword : 0x0
Property        :
```

This command modifies the ETW trace provider that has the specified GUID.
That provider is associated with a specified AutoLogger configuration named WFP-IPsec Trace.
The command sets the *Level* to have a value of 2, TRACE_LEVEL_ERROR.

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
Type: String[]
Parameter Sets: ByAutologger
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Type: String[]
Parameter Sets: ByAutologger, BySession
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Level
Specifies the maximum event level to enable for a collection.

For more information about event levels, see [EnableTraceEx2 function](https://msdn.microsoft.com/en-us/library/windows/desktop/dd392305.aspx) in MSDN.

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

Most of the time the *MatchAnyKeyword* parameter is more suitable.

For more information about keywords, see [EnableTraceEx2 function](https://msdn.microsoft.com/en-us/library/windows/desktop/dd392305.aspx) for

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

For more information about keywords, see [EnableTraceEx2 function](https://msdn.microsoft.com/en-us/library/windows/desktop/dd392305.aspx).

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

### -PassThru
Indicates that this cmdlet returns an object that represents the item on which it operates.
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

### -Property
Specifies the **EnableProperty** to use for events logged from this provider to the session.

For more information about **EnableProperty**, see [Configuring and Starting an AutoLogger Session](https://msdn.microsoft.com/en-us/library/windows/desktop/aa363687.aspx) in MSDN.

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
Type: String[]
Parameter Sets: BySession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[Configuring and Starting an Event Tracing Session](https://msdn.microsoft.com/library/windows/desktop/aa363688.aspx)

[Add-EtwTraceProvider](./Add-EtwTraceProvider.md)

[Get-EtwTraceProvider](./Get-EtwTraceProvider.md)

[Remove-EtwTraceProvider](./Remove-EtwTraceProvider.md)

