---
external help file: MSFT_DtcTransactionsStatisticsTask_v1.0.cdxml-help.xml
Module Name: MsDtc
online version: 
schema: 2.0.0
title: Get-DtcTransactionsStatistics
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: B864A4C6-F248-4685-BEE9-3DC293E01D92
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-DtcTransactionsStatistics

## SYNOPSIS
Gets a summary of transactions.

## SYNTAX

```
Get-DtcTransactionsStatistics [-DtcName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DtcTransactionsStatistics** cmdlet gets a summary of transactions being handled by the Distributed Transaction Coordinator (DTC) instance specified by the **DtcName** parameter.

## EXAMPLES

### Example 1: Get DTC transactions statistics
```
PS C:\>Get-DtcTransactionsStatistics -DtcName "Local"
Open               : 1
Committed          : 0
Aborted            : 0
ForcedAbort        : 0
InDoubt            : 0
Heuristic          : 0
SinglePhaseInDoubt : 0
OpenMax            : 1
CommittedMax       : 0
AbortedMax         : 0
InDoubtMax         : 0
HeuristicMax       : 0
```

This command gets the summary of transactions handled by the Local DTC instance.

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -DtcName
Specifies a DTC instance.
The cmdlet gets the summary of transactions for this DTC instance.
If you do not specify this parameter, or if you specify a value of Local, this cmdlet displays the summary of transactions handled by the local DTC instance.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

