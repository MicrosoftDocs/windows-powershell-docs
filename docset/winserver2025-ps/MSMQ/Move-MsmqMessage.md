---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
Module Name: MSMQ
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/msmq/move-msmqmessage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Move-MsmqMessage
---

# Move-MsmqMessage

## SYNOPSIS
Moves messages between subqueues or between the main queue and a subqueue.

## SYNTAX

```
Move-MsmqMessage -InputObject <MessageQueue> -DestinationQueue <MessageQueue> -Message <Message>
 [-Transactional] [<CommonParameters>]
```

## DESCRIPTION
The **Move-MsmqMessage** cmdlet moves messages between subqueues of the same queue or between the main queue and one of its subqueues.
This cmdlet returns a **Message** object that represents the moved message.
Move and open operations implicitly create subqueues.
You can get subqueues by using the **Get-MsmqQueue** cmdlet.

## EXAMPLES

### Example 1: Move a message to a subqueue
```
PS C:\> $SrcQueue = Get-MsmqQueue -QueueType Private -Name "MyQueue"
PS C:\> $DstQueue = Get-MsmqQueue -QueueType Private -Name "MyQueue" -SubQueue "MySubqueue"
PS C:\> $Message = $SrcQueue | Receive-MsmqQueue -Peek
PS C:\> $SrcQueue | Move-MsmqMessage -DestinationQueue $DstQueue -Message $Message
```

The first command gets a private queue named MyQueue by using the **Get-MsmqQueue** cmdlet.
The command stores the result in the $SrcQueue variable.

The second command gets a subqueue named MySubqueue by using **Get-MsmqQueue**.
The subqueue belongs to the private queue named MyQueue.
The command stores the result in the $DstQueue variable.

The third command uses the **Receive-MsmqQueue** cmdlet get message from the source queue, and stores it in the $Message variable.

The final command moves the message in $Message from the source queue to the destination queue.
The destination queue is a subqueue of MyQueue.

## PARAMETERS

### -DestinationQueue
Specifies an **MsmqQueue** object that represents the destination queue to which to move the message.
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
Specifies an **MsmqQueue** object.
The cmdlet moves the message from the source queue that this parameter specifies.
The source queue can be a subqueue or the main queue.
This parameter accepts pipeline input.

```yaml
Type: MessageQueue
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Message
Specifies a **Message** object that represents the message to move.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Msmq.PowerShell.Commands.MessageQueue

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-MsmqQueue](./Get-MsmqQueue.md)

[New-MsmqMessage](./New-MsmqMessage.md)

[Receive-MsmqQueue](./Receive-MsmqQueue.md)

