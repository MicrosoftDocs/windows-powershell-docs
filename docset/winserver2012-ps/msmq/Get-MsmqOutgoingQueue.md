---
author: Kateyanne
external help file: MSMQ_Cmdlets.xml
manager: dansimp
Module Name: MSMQ
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/msmq/get-msmqoutgoingqueue?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
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

