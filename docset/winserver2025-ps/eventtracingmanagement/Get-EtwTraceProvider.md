---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_EtwTraceProvider_v1.0.cdxml-help.xml
Module Name: EventTracingManagement
ms.date: 01/05/2017
online version: https://learn.microsoft.com/powershell/module/eventtracingmanagement/get-etwtraceprovider?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-EtwTraceProvider
---

# Get-EtwTraceProvider

## SYNOPSIS
Enumerates existing AutoLogger session configurations.

## SYNTAX

### ByAutologger (Default)
```
Get-EtwTraceProvider [[-Guid] <String[]>] [-AutologgerName <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### BySession
```
Get-EtwTraceProvider [[-Guid] <String[]>] [-SessionName <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-EtwTraceProvider** cmdlet enumerates existing AutoLogger session configurations.

## EXAMPLES

### Example 1: View all available trace providers
```
PS C:\> Get-NetEventProvider -ShowInstalled | Select-Object -Property *
```

This command obtains a list of all available ETW trace providers and their GUIDs on the current computer by using the **Get-NetEventProvider** cmdlet.
For more information, type `Get-Help Get-NetEventProvider`.

### Example 2: Get trace providers for an ETW session
```
PS C:\> Get-EtwTraceProvider -SessionName "NtfsLog"
SessionName     : NtfsLog
AutologgerName  :
Guid            : {9C88041D-349D-4647-8BFD-2C0A167BFE58}
Level           : 4
MatchAnyKeyword : 0xFFFFFFFFFFFFFFFF
MatchAllKeyword : 0x0
Property        : 0

SessionName     : NtfsLog
AutologgerName  :
Guid            : {5EEFEBDB-E90C-423A-8ABF-0241E7C5B87D}
Level           : 0
MatchAnyKeyword : 0x0
MatchAllKeyword : 0x0
Property        : 0
```

This command gets all trace providers for the ETW session named NtfsLog.

### Example 3: Get trace providers for an AutoLogger configuration
```
PS C:\> Get-EtwTraceProvider -AutologgerName "WdiContextLog"
SessionName     :
AutologgerName  : WdiContextLog
Guid            : 1D75856D-36A7-4ECB-A3F5-B13152222D29
Level           : 0
MatchAnyKeyword : 0x0
MatchAllKeyword : 0x0
Property        : 0

SessionName     :
AutologgerName  : WdiContextLog
Guid            : {1D75856D-36A7-4ECB-A3F5-B13152222D29}
Level           : 0
MatchAnyKeyword : 0x0
MatchAllKeyword : 0x0
Property        : 0
```

This command gets all trace providers for the AutoLogger configuration named WdiContextLog.

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

### -Guid
Specifies the provider ID.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Configuring and Starting an AutoLogger Session](https://msdn.microsoft.com/library/windows/desktop/aa363687.aspx)

[Configuring and Starting an Event Tracing Session](https://msdn.microsoft.com/library/windows/desktop/aa363688.aspx)

[Add-EtwTraceProvider](./Add-EtwTraceProvider.md)

[Remove-EtwTraceProvider](./Remove-EtwTraceProvider.md)

[Set-EtwTraceProvider](./Set-EtwTraceProvider.md)

