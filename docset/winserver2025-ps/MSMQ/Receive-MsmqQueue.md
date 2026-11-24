---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
Module Name: MSMQ
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/msmq/receive-msmqqueue?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Receive-MsmqQueue
---

# Receive-MsmqQueue

## SYNOPSIS
Does a destructive read from a queue.

## SYNTAX

### Transactional (Default)
```
Receive-MsmqQueue -InputObject <MessageQueue> [-Transactional] [-RetrieveBody] [-Timeout <TimeSpan>]
 [-Count <Int32>] [<CommonParameters>]
```

### Peek
```
Receive-MsmqQueue -InputObject <MessageQueue> [-Peek] [-RetrieveBody] [-Timeout <TimeSpan>] [-Count <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Receive-MsmqQueue** cmdlet does a destructive read from a queue.
The cmdlet returns the received **System.Messaging.Message** object.
This cmdlet accepts values for the **Name** parameter of path names, format names, and direct format names.
Some other Message Queuing (also known as MSMQ) cmdlets require a friendly name for the queue.
If you specify the **Peek** parameter, the cmdlet peeks at the message instead of doing a destructive read.
The cmdlet succeeds if it returns at least one message.

If you specify the **Peek** parameter, this cmdlet returns the number of messages  that is the minimum of the number supplied by the **Count** parameter and the number of messages in the queue.

## EXAMPLES

### Example 1: Perform a transacted read
```powershell
PS C:\> Get-MsmqQueue -Name "a04bm10\private$\order_queue" | Receive-MsmqQueue -Transactional
```

This command gets the specified queue by using the **Get-MsmqQueue** cmdlet.
The command passes the result to the current cmdlet by using the pipeline operator.
The current cmdlet performs a transacted read on the queue.

## PARAMETERS

### -Count
Specifies the number of messages to be returned.
The default value is 1.
You must specify a value larger than 0.

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
Accept pipeline input: True (ByValue)
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
Indicates that the cmdlet performs a transacted receive.

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

### CommonParameters
This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Msmq.PowerShell.Commands.MessageQueue

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Clear-MsmqQueue](./Clear-MSMQQueue.md)

[Get-MsmqQueue](./Get-MsmqQueue.md)

[New-MsmqQueue](./New-MsmqQueue.md)

[Remove-MsmqQueue](./Remove-MsmqQueue.md)

[Send-MsmqQueue](./Send-MsmqQueue.md)

[Set-MsmqQueue](./Set-MsmqQueue.md)

