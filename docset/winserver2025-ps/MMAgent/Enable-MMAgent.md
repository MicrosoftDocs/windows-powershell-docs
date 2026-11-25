---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ps_mmagent_v1.0.cdxml-help.xml
Module Name: MMAgent
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/mmagent/enable-mmagent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-MMAgent
---

# Enable-MMAgent

## SYNOPSIS
Enables application launch prefetching, operation recorder API functionality, page combining, and application prelaunch.

## SYNTAX

```
Enable-MMAgent [-ApplicationLaunchPrefetching] [-OperationAPI] [-PageCombining] [-ApplicationPreLaunch]
 [-MemoryCompression] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-MMAgent** cmdlet enables any or all of the following features:
- Application launch prefetching
- Operation recorder API functionality
- Page combining
- Application prelaunching

Specify the *ApplicationLaunchPrefetching* parameter to help improve application startup performance.
Application launch prefetching causes the memory manager agent to monitor the data and code that applications access.
The memory management agent then uses that information to preload the data and code into physical memory for subsequent startups.

Specify the *ApplicationPreLaunch* parameter to help improve application startup performance.
Application prelaunch can speculatively launch applications that the user is likely to use in the near future, thus reducing application switch time.

Specify the *OperationAPI* parameter to help speed up operations that repeatedly access the same file data.
Enabling this feature exposes the Windows prefetching mechanism as a public interface.

Specify the *PageCombining* parameter to help reduce the physical memory that the operating system uses.
Page combining causes the memory manager to periodically combine pages in physical memory that have identical content.

## EXAMPLES

### Example 1: Enable application launch prefetching
```
PS C:\> Enable-MMAgent -ApplicationLaunchPrefetching
```

This command enables application launch prefetching on the local computer.

## PARAMETERS

### -ApplicationLaunchPrefetching
Indicates that the cmdlet enables application launch prefetching.

If you do not specify this parameter, application launch prefetching remains in its current state, either enabled or disabled.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: alp

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationPreLaunch
Indicates that the cmdlet enables application prelaunch.

If you do not specify this parameter, application prelaunch remains in its current state, either enabled or disabled.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: apl

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -MemoryCompression
Indicates that this cmdlet uses memory compression.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: mc

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OperationAPI
Indicates that the cmdlet enables operation recorder API functionality.

If you do not specify this parameter, operation recorder API functionality remains in its current state, either enabled or disabled.

For more information about the Operation Recorder API, see[Operation Recorder](https://msdn.microsoft.com/library/windows/desktop/hh437575.aspx) on MSDN.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: oa

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PageCombining
Indicates that the cmdlet enables page combining.

If you do not specify this parameter, page combining remains in its current state, either enabled or disabled.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: pc

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

[Debug-MMAppPrelaunch](./Debug-MMAppPrelaunch.md)

[Get-MMAgent](./Get-MMAgent.md)

[Set-MMAgent](./Set-MMAgent.md)

[Disable-MMAgent](./Disable-MMAgent.md)

