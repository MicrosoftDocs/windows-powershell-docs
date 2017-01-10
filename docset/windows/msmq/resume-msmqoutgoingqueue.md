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
title: Resume-MsmqOutgoingQueue
ms.assetid: FEBE380E-6798-417D-A3BC-79CD6BB13D64
---

# Resume-MsmqOutgoingQueue

## SYNOPSIS
Resumes outgoing queues.

## SYNTAX

```
Resume-MsmqOutgoingQueue [-InputObject <OutgoingQueue[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Resume-MsmqOutgoingQueue** cmdlet resumes outgoing queues.
Specify queues to resume by using **MsmqOutgoingQueue** objects.
The cmdlet returns the resumed **MsmqOutgoingQueue** objects.

## EXAMPLES

### Example 1: Resume outgoing queues specified by name
```
PS C:\>Get-MsmqOutgoingQueue -Name "Order*" | Resume-MsmqOutgoingQueue
```

This command gets the outgoing queues have names that start with the string Order by using the Get-MsmqOutgoingQueue cmdlet.
The command passes the results to the current cmdlet by using the pipeline operator.
The current cmdlet resumes the queues.

## PARAMETERS

### -InputObject
Specifies an array of **MsmqOutgoingQueue** objects.
This cmdlet resumes outgoing queues that this parameter specifies.
This parameter accepts pipeline input.

```yaml
Type: OutgoingQueue[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

[Get-MsmqOutgoingQueue](./Get-MSMQOutgoingQueue.md)

[Suspend-MsmqOutgoingQueue](./Suspend-MsmqOutgoingQueue.md)

