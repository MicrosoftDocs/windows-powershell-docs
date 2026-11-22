---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BranchCacheOrchestrator.cdxml-help.xml
Module Name: BranchCache
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/branchcache/set-bcminsmblatency?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-BCMinSMBLatency
---

# Set-BCMinSMBLatency

## SYNOPSIS
Sets the minimum latency that must exist between client and server before transparent caching functions are utilized.

## SYNTAX

```
Set-BCMinSMBLatency [-LatencyMilliseconds] <UInt32> [-Force] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-BCMinSMBLatency** cmdlet sets the minimum latency that must exist between client and server before transparent caching functions are used.
Use this cmdlet to specify when client computers in branch offices start caching content from content servers based on the network latency, or delay, that occurs when the clients download content over a Wide Area Network (WAN) link.
When a value for this cmdlet is specified, which is the maximum round trip network latency allowed before caching begins, clients do not cache content until the network latency reaches the specified value; when network latency is greater than the value, clients begin caching content after they receive it from the content servers.

For example, if the round trip network latency value is set to zero (0), the client computers always cache content that they receive from the content servers, no matter how high or low the network latency is between their request for a file and their receipt of the file from the content server.
In another example, if the round trip network latency value is set to 100 milliseconds, then the clients do not cache content that they receive before 100 milliseconds pass, but they do begin to cache content that they receive after 100 milliseconds pass.

By default, the value of this setting is `80` milliseconds.
To make sure that client computers always cache content, set the network latency value to 0.

To prevent caching except in circumstances where network latency is very long, set the latency value to a very high value.
If a high value is used, however, then it is possible that network latency will not reach this long a delay, in which case BranchCache is disabled on your network.

Whether this setting is disabled or not configured, the client computer will cache network files if the round trip network latency of the wide area network (WAN) link is above 80 milliseconds.

## EXAMPLES

### Example 1: Set minimal latency
```
PS C:\> Set-BCMinSMBLatency -LatencyMilliseconds 20
```

This command sets the minimum latency that must exist between client and server before transparent caching functions are used to 20 milliseconds.

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

### -Force
Forces the command to run without asking for user confirmation.

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

### -LatencyMilliseconds
Specifies the minimum latency that must exist between client and server before BranchCache begins caching content.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Disable-BC](./Disable-BC.md)

[Reset-BC](./Reset-BC.md)

