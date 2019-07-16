---
external help file: MSFT_DtcTransactionsTraceSessionTask_v1.0.cdxml-help.xml
Module Name: MsDtc
online version: 
schema: 2.0.0
title: Write-DtcTransactionsTraceSession
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 1238FF18-E57F-4156-8432-FA2CFE5BA5A9
ms.author: v-anbarr
ms.reviewer: brianlic
---

# Write-DtcTransactionsTraceSession

## SYNOPSIS
Writes the data from an active DTC transactions trace session into the log file.

## SYNTAX

```
Write-DtcTransactionsTraceSession [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Write-DtcTransactionsTraceSession** cmdlet writes the data from an active Distributed Transaction Coordinator (DTC) transactions trace session into the log file.
If there is no active session, this cmdlet  exits.

## EXAMPLES

### Example 1: Write a DTC transaction trace session to a log file
```
PS C:\>Write-DtcTransactionsTraceSession
```

This command writes current DTC transaction traces session information to a log file.

## PARAMETERS

### -AsJob
{{Fill AsJob Description}}

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

[Get-DtcTransactionsTraceSession](./Get-DtcTransactionsTraceSession.md)

[Set-DtcTransactionsTraceSession](./Set-DtcTransactionsTraceSession.md)

[Start-DtcTransactionsTraceSession](./Start-DtcTransactionsTraceSession.md)

[Stop-DtcTransactionsTraceSession](./Stop-DtcTransactionsTraceSession.md)

