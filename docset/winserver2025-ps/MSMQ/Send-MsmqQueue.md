---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
Module Name: MSMQ
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/msmq/send-msmqqueue?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Send-MsmqQueue
---

# Send-MsmqQueue

## SYNOPSIS
Sends a test message to remote queues.

## SYNTAX

### Name (Default)
```
Send-MsmqQueue [-Name] <String> [-MessageObject <Message>] [-Body <Object>] [-Label <String>] [-Recoverable]
 [-Authenticated] [-Journaling] [-Transactional] [-AcknowledgeType <AcknowledgeTypes>]
 [-AdminQueuePath <String>] [-ResponseQueuePath <String>] [-TimeToReachQueue <TimeSpan>]
 [-TimeToBeReceived <TimeSpan>] [<CommonParameters>]
```

### InputObject
```
Send-MsmqQueue -InputObject <MessageQueue[]> [-MessageObject <Message>] [-Body <Object>] [-Label <String>]
 [-Recoverable] [-Authenticated] [-Journaling] [-Transactional] [-AcknowledgeType <AcknowledgeTypes>]
 [-AdminQueuePath <String>] [-ResponseQueuePath <String>] [-TimeToReachQueue <TimeSpan>]
 [-TimeToBeReceived <TimeSpan>] [<CommonParameters>]
```

## DESCRIPTION
The **Send-MsmqQueue** cmdlet sends a test message to one or more remote queues.
This cmdlet accepts values for the *Name* parameter of path names, format names, and direct format names.
Some other Message Queuing (also known as MSMQ) cmdlets require a friendly name for the queue.
By default, this cmdlet sends express messages.
It returns a **System.Messaging.Message** object that represents the message sent.

## EXAMPLES

### Example 1: Send a test message to a queue
```
PS C:\> Get-MsmqQueue -Name "a04bm10\private$\order_queue" | Send-MsmqQueue -AdminQueuePath ".\private$\admin_queue" -Recoverable -Transactional
```

This command gets a queue that has the specified name by using the **Get-MsmqQueue** cmdlet.
The command passes the results to the current cmdlet by using the pipeline operator.
The current cmdlet sends a test message to the queue.
The cmdlet specifies properties of the message.

### Example 2: Send a test message with a label to a queue
```
PS C:\> Get-MsmqQueue -Name "FormatName:DIRECT=TCP:10.199.37.61\order_queue" | Send-MsmqQueue -Label "From PowerShell" -Transactional
```

This command gets a queue that has the specified name by using **Get-MsmqQueue**.
The command passes the results to the current cmdlet by using the pipeline operator.
The current cmdlet sends a test message to the queue.
The test message has a label.

## PARAMETERS

### -AcknowledgeType
Specifies the type of acknowledgement messages that can be returned by Messaging Queuing.

```yaml
Type: AcknowledgeTypes
Parameter Sets: (All)
Aliases:
Accepted values: None, PositiveArrival, PositiveReceive, NotAcknowledgeReachQueue, FullReachQueue, NegativeReceive, NotAcknowledgeReceive, FullReceive

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdminQueuePath
Specifies a path.
The queue that the path specifies receives the acknowledgement messages that Message Queuing generates.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Authenticated
Indicates that the cmdlet sends the message as an authenticated message.

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

### -Body
Specifies the body of the message.
The cmdlet sends a message that includes the body that this parameter specifies to the queue.

```yaml
Type: Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies an array of **MessageQueue** objects.
This cmdlet sends messages to the destination queues that the **MessageQueue** specify.
This parameter accepts pipeline input.

```yaml
Type: MessageQueue[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Journaling
Indicates that the originating computer keeps a copy of the message in a journal.

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

### -Label
Specifies a label.
The label that this parameter specifies describes the message.
The default value is an empty string.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MessageObject
Specifies a preconstructed message object that you can specify as pipeline input.

```yaml
Type: Message
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a name.

```yaml
Type: String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Recoverable
Indicates that the cmdlet sends the message as a recoverable message.

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

### -ResponseQueuePath
Specifies a path.
The queue that this parameter specifies receives application-generated response messages.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeToBeReceived
Specifies the maximum amount of time, in milliseconds, for the message to be received from the destination queue.
The default value is 49.17:02:47.295.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: TTBR

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeToReachQueue
Specifies the maximum amount of time, in milliseconds, for the message to reach the queue.
The default value is 49.17:02:47.295.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: TTRQ

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Transactional
Indicates that this cmdlet sends the message as a transactional message.

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

### Microsoft.Msmq.PowerShell.Commands.MessageQueue[]

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Clear-MsmqQueue](./Clear-MSMQQueue.md)

[Get-MsmqQueue](./Get-MsmqQueue.md)

[New-MsmqQueue](./New-MsmqQueue.md)

[Receive-MsmqQueue](./Receive-MsmqQueue.md)

[Remove-MsmqQueue](./Remove-MsmqQueue.md)

[Set-MsmqQueue](./Set-MsmqQueue.md)

