---
external help file: MSMQ_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 33D16DB3-A890-478C-B0C5-B874FA584AAB
manager: dansimp
---

# Get-MsmqOutgoingQueue

## SYNOPSIS
Gets an array of MsmqOutgoingQueue objects, each representing a transactional or non-transactional outgoing queue.

## SYNTAX

```
Get-MsmqOutgoingQueue [[-Name] <String[]>]
```

## DESCRIPTION
The **Get-MsmqOutgoingQueue** cmdlet returns an array of **MsmqOutgoingQueue** objects, each representing a transactional or non-transactional outgoing queue.
The outgoing queue must be local to the machine on which the cmdlet is executed.
Without parameters, this cmdlet returns all outgoing queues of the host machine.

## EXAMPLES

### Example 1: Get an array of Outgoing queue objects specified by name
```
PS C:\>Get-MsmqOutgoingQueue -Name Order*
```

This command gets an array of outgoing queue objects that have the wildcard named Order.

## PARAMETERS

### -Name
Specifies an array that contains the name of the outgoing queue.
This parameter supports wildcard characters.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True(ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Clear-MsmqOutgoingQueue](./Clear-MsmqOutgoingQueue.md)

[Resume-MsmqOutgoingQueue](./Resume-MsmqOutgoingQueue.md)

[Suspend-MsmqOutgoingQueue](./Suspend-MsmqOutgoingQueue.md)

