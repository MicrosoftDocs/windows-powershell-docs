---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_DtcTransactionsTraceSessionTask_v1.0.cdxml-help.xml
Module Name: MsDtc
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/msdtc/get-dtctransactionstracesession?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DtcTransactionsTraceSession
---

# Get-DtcTransactionsTraceSession

## SYNOPSIS
Gets the DTC transactions trace session specific setting of the host.

## SYNTAX

```
Get-DtcTransactionsTraceSession [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-DtcTransactionsTraceSession** cmdlet gets the Distributed Transaction Coordinator (DTC) transactions trace session specific setting of the host.
All DTC instances on a single host share trace settings.

## EXAMPLES

### Example 1: Get DTC transactions trace session
```
PS C:\> Get-DtcTransactionsTraceSession
BufferCount SessionStatus               PSComputerName
----------- -------------               --------------
25          Stopped
```

This command queries the summary of transactions trace session on the local host.

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

### DtcTransactionsTraceSession
This cmdlet returns a **DtcTransactionsTraceSession** object that contains trace setting information.

## NOTES

## RELATED LINKS

[Set-DtcTransactionsTraceSession](./Set-DtcTransactionsTraceSession.md)

[Start-DtcTransactionsTraceSession](./Start-DtcTransactionsTraceSession.md)

[Stop-DtcTransactionsTraceSession](./Stop-DtcTransactionsTraceSession.md)

[Write-DtcTransactionsTraceSession](./Write-DtcTransactionsTraceSession.md)

