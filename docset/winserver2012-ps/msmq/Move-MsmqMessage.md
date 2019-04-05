---
external help file: MSMQ_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 5F7B7FB1-A749-4637-87CF-AC1E8DD7C588
manager: dansimp
---

# Move-MsmqMessage

## SYNOPSIS
Moves messages between subqueues of the same queue or between the main queue and one of its subqueues.

## SYNTAX

```
Move-MsmqMessage [-Transactional] -DestinationQueue <MessageQueue> -InputObject <MessageQueue>
 -Message <Message>
```

## DESCRIPTION
The **Move-MsmqMessage** cmdlet moves messages between subqueues of the same queue or between the main queue and one of its subqueues.
The cmdlet returns a **Message** object representing the message that was moved.
Subqueues are created by this cmdlet implicitly on move or open operations.
You can get subqueues with the Get-MsmqQueue cmdlet.

## EXAMPLES

### Example 1: Move a message between two queues
```
PS C:\>$SrcQueue = Get-MSMQQueue -Private -Name "MyQueue" 
PS C:\> $DstQueue = Get-Message = $SrcQueue | Receive-MSMQQueue -Peek -MSMQQueue -Private -Name "MyQueue" -SubQueue "MySubQueue"
PS C:\> $SrcQueue | Move-MSMQMessage -DestinationQueue $DstQueue -Message $Message
```

The first command gets a private queue named MyQueue and stores it in the variable named $SrcQueue.
The second command gets a message from $SrcQueue and stores the result in the variable named $DstQueue.
The final command moves the message from $SrcQueue and stores it in the destination queue.

## PARAMETERS

### -DestinationQueue
Specifies an **MsmqQueue** object that represents the destination queue to which the message will be moved.
The destination queue can be a subqueue or the main queue.

```yaml
Type: MessageQueue
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies an **MsmqQueue** object that represents the source queue from which the message will be moved.
The source queue can be a subqueue or the main queue.

```yaml
Type: MessageQueue
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByValue)
Accept wildcard characters: False
```

### -Message
Specifies a **Message** object representing the message to be moved.

```yaml
Type: Message
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Transactional
Indicates that this cmdlet moves the message within a transaction context.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

