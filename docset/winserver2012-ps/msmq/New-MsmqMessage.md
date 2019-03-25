---
external help file: MSMQ_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 261EF2F0-A0F8-4398-8A42-FD9A9F53AF59
manager: dansimp
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
PS C:\>New-MsmqMessage â€"Body "Test Message" â€"Recoverable â€"AdminQueue ".\private$\adminqueue"
```

This command creates a message object with body text named Test Message.

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

