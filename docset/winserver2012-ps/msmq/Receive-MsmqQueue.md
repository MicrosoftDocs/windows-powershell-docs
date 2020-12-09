---
external help file: MSMQ_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 630524E4-7523-43E3-A140-808537F8F98F
manager: dansimp
---

# Receive-MsmqQueue

## SYNOPSIS
Performs a destructive read from a queue.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Receive-MsmqQueue [-Count <Int32>] [-RetrieveBody] [-Timeout <TimeSpan>] [-Transactional]
 -InputObject <MessageQueue>
```

### UNNAMED_PARAMETER_SET_2
```
Receive-MsmqQueue [-Count <Int32>] [-Peek] [-RetrieveBody] [-Timeout <TimeSpan>] -InputObject <MessageQueue>
```

## DESCRIPTION
The **Receive-MsmqQueue** cmdlet performs a destructive read from a queue.
The **Name** parameter accepts path names, format names, and direct format names, unlike other MSMQ cmdlets that accept only a friendly name for the queue.
If the **Peek** parameter is specified, this cmdlet peeks at the message instead of doing a destructive read.
This cmdlet also writes the received **System.Messaging.Message** object to the pipeline.
This cmdlet succeeds when at least one messages is returned.
If the **Peek** parameter is supplied, the number of messages returned by this cmdlet is the minimum number supplied by the parameter **Count** and the number of messages in the queue.

## EXAMPLES

### Example 1: Peek at a MsmqQueue message instead of doing a destructive read
```
PS C:\>Get-MsmqQueue -Name "a04bm10\private$\order_queue" | Receive-MsmqQueue -Transactional -Peek
```

This command peeks at the queue named a04bm10\private$\order_queue and does not perform a destructive read.

## PARAMETERS

### -Count
Specifies the number of messages to be returned.
This value must be greater than 0.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies a **MessageQueue** object that represents the queue from which the message will be read from.

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

### -Peek
Indicates that this cmdlet returns a copy of the first message in the queue without removing the message from the queue.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetrieveBody
Indicates that this cmdlet returns the body of the message.

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

### -Timeout
Specifies the time in milliseconds that specifies the maximum time to wait for the queue to contain a message.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Transactional
Indicates that this cmdlet performs a transacted retrieval.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

[Clear-MsmqQueue](./Clear-MsmqQueue.md)

[Get-MsmqQueue](./Get-MsmqQueue.md)

[New-MsmqQueue](./New-MsmqQueue.md)

[Remove-MsmqQueue](./Remove-MsmqQueue.md)

[Send-MsmqQueue](./Send-MsmqQueue.md)

[Set-MsmqQueue](./Set-MsmqQueue.md)

