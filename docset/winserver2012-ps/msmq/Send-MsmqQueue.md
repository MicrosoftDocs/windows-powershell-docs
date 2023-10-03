---
external help file: MSMQ_Cmdlets.xml
Module Name: MSMQ
online version: https://learn.microsoft.com/powershell/module/msmq/send-msmqqueue?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Send-MsmqQueue

## SYNOPSIS
Sends a test message to the specified queues.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Send-MsmqQueue [-Name] <String> [-AcknowledgeType] [-AdminQueuePath <String>] [-Authenticated] [-Body <Object>]
 [-Journaling] [-Label <String>] [-MessageObject <Message>] [-Recoverable] [-ResponseQueuePath <String>]
 [-TimeToBeReceived <TimeSpan>] [-TimeToReachQueue <TimeSpan>] [-Transactional]
```

### UNNAMED_PARAMETER_SET_2
```
Send-MsmqQueue [-AcknowledgeType] [-AdminQueuePath <String>] [-Authenticated] [-Body <Object>] [-Journaling]
 [-Label <String>] [-MessageObject <Message>] [-Recoverable] [-ResponseQueuePath <String>]
 [-TimeToBeReceived <TimeSpan>] [-TimeToReachQueue <TimeSpan>] [-Transactional] -InputObject <MessageQueue[]>
```

## DESCRIPTION
The **Send-MsmqQueue** cmdlet sends a test message to one or more remote queues.
Note that the **Name** parameter accepts path names, format names and direct format names, unlike other MSMQ cmdlets that accept only a friendly name for the queue.
This cmdlet sends express messages by default.
It returns a **System.Messaging.Message** object that represents the message sent.

## EXAMPLES

### Example 1: Send a test message to a local queue
```
PS C:\>Get-MsmqQueue -Name "order_queue" | Send-MsmqQueue -Recoverable -Label "From Windows PowerShell"
```

This command sends a non-transactional recoverable test message to the local queue named "order_queue" with a label named "From Windows PowerShell". Recoverable messages are written to disk and resilient to system crashes for guaranteed delivery.

### Example 2: Send a test message to a remote queue with a label
```
PS C:\>Send-MsmqQueue -Name "FormatName:DIRECT=TCP:10.199.37.61\order_queue" -Transactional -Label "From Windows PowerShell"
```

This command sends a transactional test message to the remote queue named "FormatName:DIRECT=TCP:10.199.37.61\order_queue" with a label named "From Windows PowerShell".

## PARAMETERS

### -AcknowledgeType
```yaml
Type: SwitchParameter
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
Specifies the pathname of the queue that receives the acknowledgement messages that Message Queuing generates.

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
Indicates that this cmdlet sends the message as an authenticated message.

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
Specifies the body of the message to be sent to the queue.

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
Specifies an array of **MessageQueue** objects that represent the destination queues to which the message will be sent.
This parameter accepts pipelined input.

```yaml
Type: MessageQueue[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByValue)
Accept wildcard characters: False
```

### -Journaling
Indicates whether a copy of the message should be kept in a machine journal on the originating computer.

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
Specifies a label that describes the message.

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
Specifies a pre-constructed message object that can be passed in as pipelined input.

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
Specifies the name of the queue.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Recoverable
Indicates that this cmdlet sends the message as a recoverable message.

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
Specifies the pathname of the queue that receives application-generated response messages.

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
Specifies the maximum amount of time for the message to be received from the destination queue.
The default value for this parameter is 49.17:02:47.295.

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
Specifies the maximum amount of time for the message to reach the queue.
The default value for this parameter is 49.17:02:47.295.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Clear-MsmqQueue](./Clear-MsmqQueue.md)

[Get-MsmqQueue](./Get-MsmqQueue.md)

[New-MsmqQueue](./New-MsmqQueue.md)

[Receive-MsmqQueue](./Receive-MsmqQueue.md)

[Remove-MsmqQueue](./Remove-MsmqQueue.md)

[Set-MsmqQueue](./Set-MsmqQueue.md)
