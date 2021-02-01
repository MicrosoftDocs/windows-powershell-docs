---
external help file: Microsoft.Protocols.Tools.PowerShell.dll-Help.xml
Module Name: PEF
online version: 
schema: 2.0.0
title: Stop-PefTraceSession
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 6530AD50-77CB-471D-BF1C-54FE000C0380
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Stop-PefTraceSession

## SYNOPSIS
Stops a PEF Trace Session.

## SYNTAX

```
Stop-PefTraceSession [-PEFSession] <IPpkTraceSession> [-Trigger <Trigger[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-PefTraceSession** cmdlet creates an action that stops a Protocol Engineering Framework (PEF) Trace Session.
You can also specify a trigger that causes the Trace Session to stop.
Use this cmdlet to define a stop action before you start a PEF Trace Session.

When a Trace Session stops, the session disposes of all message data and any other information.
To store the message data from theTrace Session, use the **SaveOnStop** parameter when you create the Trace Session object with the New-PefTraceSession cmdlet.
You can also use the Save-PefDataCollection cmdlet to save the message data.

## EXAMPLES

### Example 1: Define a stop action for a Trace Session
```
PS C:\> $TraceSession01 = New-PefTraceSession -Mode Circular -Path "C:\Traces\Result.matu" -Name ".\Trace01.matu" -SaveOnStop
PS C:\> Add-PefMessageSource -PEFSession $TraceSession01 -Source "Microsoft-Pef-WFP-MessageProvider"
PS C:\> $Trigger01 = New-PefMessageTrigger -Filter "icmp"
PS C:\> Stop-PefTraceSession -PEFSession $TraceSession01 -Trigger $Trigger01
PS C:\> Start-PefTraceSession -PEFSession $TraceSession01
```

This example creates a PEF Trace Session that includes a stop action.

The first command creates a Trace Session and stores it in the **$TraceSession01** variable.
This command also specifies the Circular capture mode.
The command uses the **SaveOnStop** parameter and specifies an input file containing message data for the Trace Session as Trace01.matu, located in the current directory, and an output file to contain the captured data, Result.matu, also in the current directory.

The second command uses the Add-PefMessageSource cmdlet to specify a provider for the Trace Session object stored in the **$TraceSession01** variable.

The third command uses the New-PefMessageTrigger  cmdlet to create a message trigger object and stores it in the **$Trigger01** variable.

The fourth command creates a stop action for the Trace Session stored in the **$TraceSession01** variable and specifies the trigger stored in the **$Trigger01** variable.

The fifth command uses the Start-PefTraceSession cmdlet to start the PEF Trace Session stored in the **$TraceSession01** variable.

## PARAMETERS

### -PEFSession
Specifies an object that contains a Trace Session.
To create a Trace Session, use the New-PefTraceSession cmdlet.

```yaml
Type: IPpkTraceSession
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Trigger
Specifies an array of **Trigger** objects.
When one of these triggers runs, the action stops the Trace Session.

```yaml
Type: Trigger[]
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

[Add-PefMessageSource](./Add-PefMessageSource.md)

[New-PefDateTimeTrigger](./New-PefDateTimeTrigger.md)

[New-PefKeyDownTrigger](./New-PefKeyDownTrigger.md)

[New-PefMessageTrigger](./New-PefMessageTrigger.md)

[New-PefProcessTrigger](./New-PefProcessTrigger.md)

[New-PefTimeSpanTrigger](./New-PefTimeSpanTrigger.md)

[New-PefTraceSession](./New-PefTraceSession.md)

[Save-PefDataCollection](./Save-PefDataCollection.md)

[Start-PefTraceSession](./Start-PefTraceSession.md)

