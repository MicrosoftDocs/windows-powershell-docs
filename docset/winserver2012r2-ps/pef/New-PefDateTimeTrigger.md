---
external help file: Microsoft.Protocols.Tools.PowerShell.dll-Help.xml
Module Name: PEF
online version: 
schema: 2.0.0
title: New-PefDateTimeTrigger
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 325863B7-C9D9-4053-93B7-2ABE21AA4D4E
ms.author: v-anbarr
ms.reviewer: brianlic
---

# New-PefDateTimeTrigger

## SYNOPSIS
Creates a trigger that signals at the specified time.

## SYNTAX

```
New-PefDateTimeTrigger [-DateTime] <DateTime> [-Repeat] [<CommonParameters>]
```

## DESCRIPTION
The **New-PefDateTimeTrigger** cmdlet creates a trigger that signals at the specified time.
You can use a date-time trigger to start or stop a Protocol Engineering Framework (PEF) Trace Session, or trigger other actions, on the date and time that you specify.
The trigger becomes active when you associate it to a PEF action.

## EXAMPLES

### Example 1: Add a Trace Filter by using a date-time trigger
```
PS C:\> $TraceSession01 = New-PefTraceSession -Mode Circular
PS C:\> $TriggerTime = Get-Date -Year 2013 -Month 1 -Day 31 -Hour 3 -Minute 0 -Second 0
PS C:\> $Trigger02 = New-PefDateTimeTrigger -DateTime $TriggerTime 
PS C:\> Set-PefTraceFilter -PEFSession $TraceSession01 -Filter "icmp" -Trigger $Trigger02
PS C:\> Add-PefMessageSource -Source "Microsoft-Pef-WFP-MessageProvider"
PS C:\> Start-PefTraceSession -PEFSession $TraceSession01
```

This example adds a Trace Filter to a Trace Session at 3am on January 31, 2013.
The first command uses the New-PefTraceSession cmdlet to create a PEF Trace Session object and store it in the **$TraceSession01** variable.

The second command uses the Get-Datehttp://go.microsoft.com/fwlink/?LinkID=293966 cmdlet to create a **DateTime** object, and then stores in the **$TriggerTime** variable.
For more information, type `Get-Help Get-Date`.
You can specify a future time, but no more than 25 days in the future.

The third command uses the New-PefDateTimeTrigger cmdlet to create a trigger with the **DateTime** value that is stored in the **$TriggerTime** variable.
The command stores the trigger in the **$Trigger02** variable.

The fourth command uses the Set-PefTraceFilter to specify a Trace Filter with the string value "icmp" for the Trace Session stored in the **$TraceSession01** variable.
This command also specifies the trigger stored in the **$Trigger02** variable, which adds the specified Trace Filter to the Trace Session at 3am on January 31, 2013.

The fifth command uses the Add-PefMessageSource cmdlet to specify a provider for the Trace Session object stored in the **$TraceSession01** variable.

The final command uses the Start-PefTraceSession cmdlet to start the Trace Session stored in the **$TraceSession01** variable.

## PARAMETERS

### -DateTime
Specifies a **DateTime** object.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Repeat
Indicates that the trigger runs on each occurrence of the date and time that you specify.
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

[Get-Date](http://go.microsoft.com/fwlink/?LinkID=293966)

[Add-PefMessageSource](./Add-PefMessageSource.md)

[New-PefKeyDownTrigger](./New-PefKeyDownTrigger.md)

[New-PefMessageTrigger](./New-PefMessageTrigger.md)

[New-PefProcessTrigger](./New-PefProcessTrigger.md)

[New-PefTimeSpanTrigger](./New-PefTimeSpanTrigger.md)

[New-PefTraceSession](./New-PefTraceSession.md)

[Set-PefTraceFilter](./Set-PefTraceFilter.md)

[Start-PefTraceSession](./Start-PefTraceSession.md)

