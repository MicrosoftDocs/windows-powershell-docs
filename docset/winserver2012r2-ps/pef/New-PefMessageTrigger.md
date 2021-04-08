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
online version: https://docs.microsoft.com/powershell/module/pef/new-pefmessagetrigger?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-PefMessageTrigger
---

# New-PefMessageTrigger

## SYNOPSIS
Creates a trigger based on detecting a filter match for a specific message in a PEF Trace Session.

## SYNTAX

```
New-PefMessageTrigger [-PEFSession] <IPpkTraceSession> [-Filter] <String> [-Repeat] [<CommonParameters>]
```

## DESCRIPTION
The **New-PefMessageTrigger** cmdlet creates a trigger based on detecting a filter match for a specific message in a PEF Trace Session.
You can use a message trigger to start, stop, save, and filter a Protocol Engineering Framework (PEF) Trace Session based on any valid filter, for example, a protocol name such as ARP or ICMP.
The trigger becomes active when you associate it to a PEF action.

## EXAMPLES

### Example 1: Stop a Trace Session based on a filtered message type
```
PS C:\> $TraceSession01 = New-PefTraceSession -Mode Linear -Name ".\myTrace.matu" -SaveOnStop -Path "C:\Traces\Result.matu"
PS C:\> Add-PefMessageSource -PEFSession $TraceSession01 -Source "Microsoft-PEF-WFP-MessageProvider"
PS C:\> $Trigger01 = New-PefMessageTrigger -Filter "icmp"
PS C:\> Stop-PefTraceSession -PEFSession $TraceSession01 -Trigger $Trigger01
PS C:\> Start-PefTraceSession -PEFSession $TraceSession01
```

This example starts a PEF Trace Session in linear capture mode.
The Trace Session continues until ICMP traffic is detected or certain disk quotas are reached on the computer where the Trace Session is running.

The first command uses the New-PefTraceSession cmdlet to create a Trace Session object and stores it in the **$TraceSession01** variable.
This cmdlet also uses the **Name** and **Path** parameters to specify a source file for data input and a save location for trace results, respectively.

The second command uses the Add-PefMessageSource cmdlet to specify a provider for the Trace Session stored in **$TraceSession01**.

The third command uses the New-PefMessageTrigger cmdlet to create a new message trigger object and stores it in the **$Trigger01** variable.

The fourth command uses the Stop-PefTraceSession cmdlet to create a stop action for the trigger stored in **$Trigger01** and associates that action with the Trace Session stored in **$Trace Session01**.

The fifth command uses the Start-PefTraceSession cmdlet to start the Trace Session stored in **$TraceSession01**.
The **SaveOnStop** parameter in the New-PefTraceSession cmdlet causes the Trace Session to be saved to the specified file location and format after the first ICMP protocol message is parsed.

## PARAMETERS

### -Filter
Specifies a trace filter.
You can use the Set-PefTraceFilter cmdlet to create the trace filter that defines the type of message that stops the Trace Session.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PEFSession
Specifies a PEF Trace Session.
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

### -Repeat
Indicates that a trigger runs on each occurrence of a specified event.
If you do not specify this parameter, the trigger runs only once.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-PefProcessTrigger](./New-PefProcessTrigger.md)

[New-PefTimeSpanTrigger](./New-PefTimeSpanTrigger.md)

[New-PefDateTimeTrigger](./New-PefDateTimeTrigger.md)

[New-PefKeyDownTrigger](./New-PefKeyDownTrigger.md)

[Add-PefMessageSource](./Add-PefMessageSource.md)

[Stop-PefTraceSession](./Stop-PefTraceSession.md)

[New-PefTraceSession](./New-PefTraceSession.md)

