---
author: Kateyanne
description: 
external help file: Microsoft.Protocols.Tools.PowerShell.dll-Help.xml
manager: jasgro
Module Name: PEF
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/pef/start-peftracesession?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-PefTraceSession
---

# Start-PefTraceSession

## SYNOPSIS
Starts a PEF Trace Session.

## SYNTAX

```
Start-PefTraceSession [-PEFSession] <IPpkTraceSession> [-Trigger <Trigger[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Start-PefTraceSession** cmdlet creates an action that starts a Protocol Engineering Framework (PEF) Trace Session.
You can specify a trigger for this action.

If you do not specify a new trigger or a trigger that already fired, the start action enters a message processing loop.
The Trace Session uses that loop to process messages that are delivered by the specified message providers.
The loop stops when the Trace Session stops.
A session is terminated when the  stop action occurs  or when there are no more messages to process.
Use the Stop-PefTraceSession cmdlet to create a stop action.

## EXAMPLES

### Example 1: Start a Trace Session that closes with a stop trigger
```
PS C:\> $TraceSession01 = New-PefTraceSession 
PS C:\> Add-PefMessageSource -PEFSession $TraceSession01 -Provider "Microsoft-Pef-WFP-MessageProvider"
PS C:\> $Trigger01 = New-PefMessageTrigger -Filter "icmp"
PS C:\> Stop-PefTraceSession -PEFSession $TraceSession01 -Trigger $Trigger01
PS C:\> Start-PefTraceSession -PEFSession $TraceSession01
```

This example creates and starts a PEF Trace Session.

The first command uses the New-PefTraceSession cmdlet to create a Trace Session object, and then stores it in the **$TraceSession01** variable.

The second command uses the Add-PefMessageSource cmdlet to specify a provider for the Trace Session object stored in **$TraceSession01**.

The third command uses the New-PefMessageTrigger cmdlet to create a message trigger object, and then stores it in the **$Trigger01** variable.

The fourth command uses the Stop-PefTraceSession cmdlet to create a stop action for the Trace Session, which is activated by the trigger stored in **$Trigger01**.

The last command starts the PEF Trace Session stored in **$TraceSession01**.

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

[Stop-PefTraceSession](./Stop-PefTraceSession.md)

[New-PefTraceSession](./New-PefTraceSession.md)

[New-PefDateTimeTrigger](./New-PefDateTimeTrigger.md)

[New-PefMessageTrigger](./New-PefMessageTrigger.md)

[New-PefProcessTrigger](./New-PefProcessTrigger.md)

[New-PefTimeSpanTrigger](./New-PefTimeSpanTrigger.md)

[Add-PefMessageSource](./Add-PefMessageSource.md)

