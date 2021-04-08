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
online version: https://docs.microsoft.com/powershell/module/pef/save-pefdatacollection?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Save-PefDataCollection
---

# Save-PefDataCollection

## SYNOPSIS
Saves the data from a PEF Trace Session.

## SYNTAX

```
Save-PefDataCollection [-PEFSession] <IPpkTraceSessionEx> [-Path] <String> [-Force] [-SaveAsParsed]
 [-Trigger <Trigger[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Save-PefDataCollection** cmdlet creates an action that saves the data collection of a Protocol Engineering Framework (PEF) Trace Session to a file.
This cmdlet enables you to specify the Trace Session to be saved and the path to a file in which to save the data collection.

You can also specify a trigger for the save action.
When the trigger activates, the save action saves all messages currently contained in the Trace Session.

If you want to save data when the Trace Session stops, specify the **SaveOnStop** parameter when you create the Trace Session with the New-PefTraceSession cmdlet.

## EXAMPLES

### Example 1: Save the contents of a Trace Session with a stop trigger
```
PS C:\> $TraceSession01 = New-PefTraceSession -Mode Circular -SaveOnStop
PS C:\> $Trigger01 = New-PefKeyDownTrigger -Key S
PS C:\> Save-PefDataCollection -PEFSession $TraceSession01 -Path "C:\Traces\Trace01.matu" -Force -Trigger $Trigger01
PS C:\> Start-PefCaptureSession -PEFSession $TraceSession01
```

This example creates a PEF Trace Session that you can save at any time by using the keyboard shortcut S.

The first command creates a Trace Session that runs in the Circular mode and stores a Trace Session object in the **$TraceSession01** variable.

The second command uses the New-PefKeyDownTrigger cmdlet to create a trigger based on the keyboard shortcut S, and then stores it in the **$Trigger01** variable.

The third command creates a save action for the Trace Session stored in **$TraceSession01**, which uses the trigger specified in **$Trigger01**.
The command also specifies a name for the trace file to save.
The command also uses the **Force** parameter and therefore does not prompt you before replacing an existing file.

The final command starts the Trace Session based on the configuration of the object stored in **$TraceSession01**.

## PARAMETERS

### -Force
Performs the action without a confirmation message.

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

### -PEFSession
Specifies an object that contains a Trace Session.
To create a Trace Session, use the New-PefTraceSession cmdlet.

```yaml
Type: IPpkTraceSessionEx
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Path
Specifies a file path.
The action saves the contents of a Trace Session to this file.

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

### -SaveAsParsed
Indicates that the cmdlet parses all messages fully, and saves them as a .matp file.
By default, the cmdlet saves trace data as unparsed.
The parsed data in a .matp file loads more quickly.
The operation of parsing during capture causes the cmdlet to capture data more slowly.

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

### -Trigger
Specifies an array of **Trigger** objects.
When one of these triggers runs, the associated action saves the contents of the Trace Session.

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

[New-PefDateTimeTrigger](./New-PefDateTimeTrigger.md)

[New-PefKeyDownTrigger](./New-PefKeyDownTrigger.md)

[New-PefMessageTrigger](./New-PefMessageTrigger.md)

[New-PefProcessTrigger](./New-PefProcessTrigger.md)

[New-PefTimeSpanTrigger](./New-PefTimeSpanTrigger.md)

[New-PefTraceSession](./New-PefTraceSession.md)

