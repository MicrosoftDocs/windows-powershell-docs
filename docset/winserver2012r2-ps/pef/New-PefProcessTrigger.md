---
external help file: Microsoft.Protocols.Tools.PowerShell.dll-Help.xml
Module Name: PEF
online version: 
schema: 2.0.0
title: New-PefProcessTrigger
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: A593E47C-3410-4AD9-BF42-A10D537BA6DF
ms.author: v-kaunu
ms.reviewer: brianlic
---

# New-PefProcessTrigger

## SYNOPSIS
Creates a trigger that signals when a process exits.

## SYNTAX

```
New-PefProcessTrigger [-FilePath] <String> [[-Arguments] <String>] [-Repeat] [<CommonParameters>]
```

## DESCRIPTION
The **New-PefProcessTrigger** cmdlet creates a trigger that signals when a process exits.
You can use this process trigger to invoke a process at the time you start a Protocol Engineering Framework (PEF) Trace Session with the Start-PefTraceSession cmdlet.
The trigger executes the process when it becomes associated with a PEF action.
When the process exits, the trigger signals.
The trigger becomes active when you associate it to a PEF action.

## EXAMPLES

### Example 1: Create a trigger that invokes a process
```
PS C:\> $TraceSession01 = New-PefTraceSession -Mode Linear -Name ".\myTrace.matu" -SaveOnStop -Path "C:\Traces\result.matu" -Force
PS C:\> Add-PefMessageSource -PEFSession $TraceSession01 -Source "Microsoft-Pef-WFP-MessageProvider"
PS C:\> Stop-PefTraceSession -PEFSession $TraceSession01 -Trigger (New-PefDateTimeTrigger ($dt=Get-Date).AddMinutes(10))
PS C:\> Start-PefTraceSession -PEFSession $TraceSession01 -Trigger (New-PefProcessTrigger -FilePath C:\Windows\system32\PING.EXE -Arguments "www.contoso.com -4")
```

This example adds a trigger to a linear PEF Trace Session that invokes the ping.exe process when the Start-PefTraceSession cmdlet runs.
The session actually starts when the ping command completes.

The first command uses the New-PefTraceSession cmdlet to create a Trace Session object and stores it in the **$TraceSession01** variable.

The second command uses the Add-PefMessageSource cmdlet to add a provider for the Trace Session stored in the **$TraceSession01** variable.

The third command uses the Stop-PefTraceSession cmdlet to stop the Trace Session stored in the **$TraceSession01** variable ten minutes after the session starts, by using the New-PefDateTimeTrigger cmdlet.

The fourth command uses the Start-PefTraceSession cmdlet to start the Trace Session stored in the **$TraceSession01** variable.
The invoked process in the example is Ping.exe, which pings a location specified by the **Arguments** parameter.
The sessions starts when the invoked process stops.
Note that the 4 parameter value forces the use of IPv4; if unspecified, the default IP transport is used.

## PARAMETERS

### -Arguments
Specifies parameters or parameter values that the cmdlet requires to invoke a process.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath
Specifies the path and file name of the executable file that is to be invoked.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Repeat
Indicates that the trigger runs on each occurrence of invoking a process.
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

[New-PefTraceSession](./New-PefTraceSession.md)

[Add-PefMessageSource](./Add-PefMessageSource.md)

[New-PefDateTimeTrigger](./New-PefDateTimeTrigger.md)

[Stop-PefTraceSession](./Stop-PefTraceSession.md)

[Start-PefTraceSession](./Start-PefTraceSession.md)

