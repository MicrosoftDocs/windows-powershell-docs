---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
Module Name: MSMQ
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/msmq/get-msmqoutgoingqueue?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-MSMQOutgoingQueue
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
PS C:\> Get-MsmqOutgoingQueue -Name "Order*"
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Clear-MsmqOutgoingQueue](./Clear-MSMQOutgoingQueue.md)

[Resume-MsmqOutgoingQueue](./Resume-MsmqOutgoingQueue.md)

[Suspend-MsmqOutgoingQueue](./Suspend-MsmqOutgoingQueue.md)

