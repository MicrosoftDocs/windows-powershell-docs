---
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
Module Name: MSMQ
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/msmq/move-msmqmessage?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
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
You can get subqueues by using the Get-MsmqQueue cmdlet.

## EXAMPLES

### Example 1
```
PS C:\> $srcQueue = Get-MsmqQueue -QueueType Private -Name "Myqueue" 
PS C:\> $dstQueue = Get-MsmqQueue -QueueType Private -Name "Myqueue" -SubQueue "MySubqueue"
PS C:\> $Message = $srcQueue | Receive-MsmqQueue -Peek
PS C:\> $srcQueue | Move-MsmqMessage -DestinationQueue $dstQueue -Message $Message
```

## PARAMETERS

### -DestinationQueue
Specifies a **MsmqQueue** object that represents the destination queue to which to move the message.
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
Specifies a **MsmqQueue** object.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-MsmqMessage](./New-MsmqMessage.md)

[Get-MsmqQueue](./Get-MsmqQueue.md)

