---
external help file: MSFT_DtcTransactionsTraceSettingTask_v1.0.cdxml-help.xml
Module Name: MsDtc
online version: 
schema: 2.0.0
title: Set-DtcTransactionsTraceSetting
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: FB2F0685-6D63-4745-B68A-423EF189C193
ms.author: v-anbarr
ms.reviewer: brianlic
---

# Set-DtcTransactionsTraceSetting

## SYNOPSIS
Modifies the DTC transactions trace setting of the host.

## SYNTAX

### TraceAllParameterSet
```
Set-DtcTransactionsTraceSetting -AllTransactionsTracingEnabled <Boolean> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### TraceSelectedParameterSet
```
Set-DtcTransactionsTraceSetting [-AbortedTransactionsTracingEnabled <Boolean>]
 [-LongLivedTransactionsTracingEnabled <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DtcTransactionsTraceSetting** cmdlet modifies the Distributed Transaction Coordinator (DTC) transactions trace setting of the host.

## EXAMPLES

### Example 1: Enable trace settings for all transactions
```
PS C:\> Set-DtcTransactionsTraceSetting -AllTransactionsTracingEnabled $True
```

This command enables trace settings for all transactions.

## PARAMETERS

### -AbortedTransactionsTracingEnabled
Indicates whether to enable tracing for aborted transactions.

```yaml
Type: Boolean
Parameter Sets: TraceSelectedParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllTransactionsTracingEnabled
Indicates whether to enable tracing for all transactions.

```yaml
Type: Boolean
Parameter Sets: TraceAllParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -LongLivedTransactionsTracingEnabled
Indicates whether to enable tracing for long-lived transactions.

```yaml
Type: Boolean
Parameter Sets: TraceSelectedParameterSet
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

[Get-DtcTransactionsTraceSetting](./Get-DtcTransactionsTraceSetting.md)

