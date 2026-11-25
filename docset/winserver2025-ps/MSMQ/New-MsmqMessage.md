---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
Module Name: MSMQ
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/msmq/new-msmqmessage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-MsmqMessage
---

# New-MsmqMessage

## SYNOPSIS
Creates a message object.

## SYNTAX

```
New-MsmqMessage [[-Body] <Object>] [-Recoverable] [-Authenticated] [-Journaling] [-Label <String>]
 [-AdminQueuePath <String>] [-AcknowledgeType <AcknowledgeTypes>] [-ResponseQueuePath <String>]
 [-TimeToReachQueue <TimeSpan>] [-TimeToBeReceived <TimeSpan>] [<CommonParameters>]
```

## DESCRIPTION
The **New-MsmqMessage** cmdlet creates a **System.Messaging.Message** object that includes properties specified by parameters.

## EXAMPLES

### Example 1: Create a test message
```
PS C:\> New-MsmqMessage -Body "Test Message" -AdminQueuePath ".\private$\adminqueue" -Recoverable
```

This command creates a test message.
The command specifies the queue that receives the acknowledgement message.

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
The default value is an empty body.

```yaml
Type: Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
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

### -Recoverable
Indicates that the cmdlet sets the recoverable property of a message object.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Object

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Move-MsmqMessage](./Move-MsmqMessage.md)

