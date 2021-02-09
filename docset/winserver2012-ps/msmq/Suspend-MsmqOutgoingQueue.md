---
external help file: MSMQ_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 9798E2C3-2CB1-403F-8FF0-82DAE207D842
manager: dansimp
---

# Suspend-MsmqOutgoingQueue

## SYNOPSIS
Suspends the specified outgoing queues.

## SYNTAX

```
Suspend-MsmqOutgoingQueue -InputObject <OutgoingQueue[]>
```

## DESCRIPTION
The **Suspend-MsmqOutgoingQueue** cmdlet suspends all outgoing queues that are represented by the supplied **MsmqOutgoingQueue** objects, and returns the suspended queue objects.

## EXAMPLES

### Example 1: Suspend an outgoing queue
```
PS C:\>Get-MsmqOutgoingQueue -Name "Order*" | Suspend-MsmqOutgoingQueue
```

This command suspends all outgoing queues that have the wildcard named Order*.

## PARAMETERS

### -InputObject
Specifies an array of **MsmqOutgoingQueue** objects that represent the outgoing queues that are to be suspended.
This parameter accepts pipelined input.

```yaml
Type: OutgoingQueue[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Clear-MsmqOutgoingQueue](./Clear-MsmqOutgoingQueue.md)

[Get-MsmqOutgoingQueue](./Get-MsmqOutgoingQueue.md)

[Resume-MsmqOutgoingQueue](./Resume-MsmqOutgoingQueue.md)

