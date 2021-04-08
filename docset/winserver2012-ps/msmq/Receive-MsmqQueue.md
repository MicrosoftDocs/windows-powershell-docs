---
author: Kateyanne
external help file: MSMQ_Cmdlets.xml
manager: dansimp
Module Name: MSMQ
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/msmq/receive-msmqqueue?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Receive-MsmqQueue

## SYNOPSIS
Does a destructive read from a queue.

## SYNTAX

### Transactional (Default)
```
Receive-MsmqQueue [-Count <Int32>] [-RetrieveBody] [-Timeout <TimeSpan>] [-Transactional]
 -InputObject <MessageQueue>
```

### Peek
```
Receive-MsmqQueue [-Count <Int32>] [-Peek] [-RetrieveBody] [-Timeout <TimeSpan>] -InputObject <MessageQueue>
```

## DESCRIPTION
The **Receive-MsmqQueue** cmdlet does a destructive read from a queue.
The cmdlet returns the received **System.Messaging.Message** object.
This cmdlet accepts values for the **Name** parameter of path names, format names, and direct format names.
Some other Message Queuing (also known as MSMQ) cmdlets require a friendly name for the queue.
If you specify the **Peek** parameter, the cmdlet peeks at the message instead of doing a destructive read.
The cmdlet succeeds if it returns at least one message.

If you specify the **Peek** parameter, this cmdlet returns the number of messages  that is the minimum of the number supplied by the **Count** parameter and the number of messages in the queue.s

## EXAMPLES

### Example 1: Peek at a MsmqQueue message instead of doing a destructive read
```powershell
PS C:\>Get-MsmqQueue -Name "a04bm10\private$\order_queue" | Receive-MsmqQueue -Transactional -Peek
```

This command peeks at the queue named a04bm10\private$\order_queue and does not perform a destructive read.

## PARAMETERS

### -Count
Specifies the number of messages to be returned.
The default value is 1.
You must specify a value greater than 0.

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
Specifies a **MessageQueue** object.
The cmdlet reads from the queue that the **MessageQueue** specifies.
This parameter accepts pipeline input.

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
Parameter Sets: Peek
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
Specifies the maximum time, in milliseconds, to wait for the queue to contain a message.
The default value is 0.

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
Parameter Sets: Transactional
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
