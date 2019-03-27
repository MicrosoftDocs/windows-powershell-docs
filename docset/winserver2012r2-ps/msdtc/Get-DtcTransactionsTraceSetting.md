---
external help file: MSFT_DtcTransactionsTraceSettingTask_v1.0.cdxml-help.xml
Module Name: MsDtc
online version: 
schema: 2.0.0
title: Get-DtcTransactionsTraceSetting
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: E717BE8B-A991-4033-A986-D6CF660FDDAB
ms.author: kenwith
ms.reviewer: brianlic
---

# Get-DtcTransactionsTraceSetting

## SYNOPSIS
Gets the DTC transactions trace setting of the host.

## SYNTAX

```
Get-DtcTransactionsTraceSetting [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-DtcTransactionsTraceSetting** cmdlet gets the Distributed Transaction Coordinator (DTC) transactions trace setting of the host.
Trace settings are shared by all DTC instances on a single host.

## EXAMPLES

### Example 1: Get DTC transactions trace setting
```
PS C:\>Get-DtcTransactionsTraceSetting
AbortedTransactionsTracingEnabled AllTransactionsTracingEnabled LongLivedTransactionsTracingEnabled PSComputerName
--------------------------------- ----------------------------- ----------------------------------- --------------
True                              False                         True
```

This command queries the transactions trace setting on the local host.

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

### DtcTransactionsTraceSettings
This cmdlet returns an object of DtcTransactionsTraceSettings containing the trace settings information.

## NOTES

## RELATED LINKS

[Set-DtcTransactionsTraceSetting](./Set-DtcTransactionsTraceSetting.md)

