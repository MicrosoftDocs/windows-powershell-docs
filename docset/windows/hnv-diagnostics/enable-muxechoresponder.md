---
author: brianlic
description: 
external help file: MuxEchoResponder-help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Enable-MuxEchoResponder
ms.assetid: 76E1FFE7-C816-49FD-BCA7-6DCC662CBCD8
---

# Enable-MuxEchoResponder

## SYNOPSIS
Enables an ICMP echo responder.

## SYNTAX

```
Enable-MuxEchoResponder [-TargetVIP] <String> [[-SequenceNumber] <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-MuxEchoResponder** cmdlet enables an ICMP echo responder in a multiplexer (MUX).

You should run this cmdlet on a MUX virtual machine, either locally or through remote PowerShell.

## EXAMPLES

### Example 1: Enable an echo responder
```
PS C:\> Enable-MuxEchoResponder -TargetVIP "10.123.176.108" -SequenceNumber 27
```

This command enables the specified echo responder.

## PARAMETERS

### -SequenceNumber
Specifies the ICMP sequence number of the echo responder to disable.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetVIP
Specifies the target virtual IP address of the echo responder to enable.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-MuxEchoResponder](./Disable-MuxEchoResponder.md)

