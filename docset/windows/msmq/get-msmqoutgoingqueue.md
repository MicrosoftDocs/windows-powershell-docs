---
author: brianlic
description: 
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-27
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-MSMQOutgoingQueue
ms.assetid: 33D16DB3-A890-478C-B0C5-B874FA584AAB
---

# Get-MsmqOutgoingQueue

## SYNOPSIS
Gets outgoing message queues.

## SYNTAX

```
Get-MsmqOutgoingQueue [[-Name] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-MsmqOutgoingQueue** cmdlet gets **MsmqOutgoingQueue** objects.
Each object represents a transactional or non-transactional outgoing queue.
This cmdlet gets outgoing queues that are local to the computer on which you run the cmdlet.
If you do not specify parameters, this cmdlet gets all outgoing queues of the host computer.

## EXAMPLES

### Example 1: Get outgoing message queues
```
PS C:\>Get-MsmqOutgoingQueue -Name "Order*"
```

This command gets all outgoing message queues that are local to the current computer that start with the string Order.

## PARAMETERS

### -Name
Specifies an array of names of queues.
The names specify outgoing queues.
This parameter supports wildcard characters.
The default value is *.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Clear-MsmqOutgoingQueue](./Clear-MSMQOutgoingQueue.md)

[Resume-MsmqOutgoingQueue](./Resume-MsmqOutgoingQueue.md)

[Suspend-MsmqOutgoingQueue](./Suspend-MsmqOutgoingQueue.md)

