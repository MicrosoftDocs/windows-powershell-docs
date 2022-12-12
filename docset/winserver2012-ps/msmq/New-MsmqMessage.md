---
external help file: MSMQ_Cmdlets.xml
Module Name: MSMQ
online version: https://learn.microsoft.com/powershell/module/msmq/new-msmqmessage?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-MsmqMessage

## SYNOPSIS
Creates a System.Messaging.Message object.

## SYNTAX

```
New-MsmqMessage [[-Body] <Object>] [-AcknowledgeType] [-AdminQueuePath <String>] [-Authenticated] [-Journaling]
 [-Label <String>] [-Recoverable] [-ResponseQueuePath <String>] [-TimeToBeReceived <TimeSpan>]
 [-TimeToReachQueue <TimeSpan>]
```

## DESCRIPTION
The **New-MsmqMessage** cmdlet creates a **System.Messaging.Message** object.

## EXAMPLES

### Example 1: Create a message object
```
PS C:\>New-MsmqMessage -Body "Test Message" -Recoverable -AdminQueue ".\private$\adminqueue"
```

This command creates a message object with body text named Test Message.

## PARAMETERS

### -AcknowledgeType
Specifies the type of acknowledgement messages that can be returned by Messaging Queuing.

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
Specifies the queue that receives the acknowledgement messages that Message Queuing generates.

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
Specifies the body of the message.

```yaml
Type: Object
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True(ByValue)
Accept wildcard characters: False
```

### -Journaling
Indicates that this cmdlet keeps a copy of the message in a machine journal on the originating computer.

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

### -Recoverable
Indicates that this cmdlet sets the recoverable property of a message object.

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
Specifies the queue that receives application-generated response messages.

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
Specifies the maximum amount of time in milliseconds for the message to be received from the destination queue.
Default is 49.17:02:47.295.

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
Specifies the maximum amount of time in milliseconds for the message to reach the queue.
Default is 49.17:02:47.295.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Move-MsmqMessage](./Move-MsmqMessage.md)

