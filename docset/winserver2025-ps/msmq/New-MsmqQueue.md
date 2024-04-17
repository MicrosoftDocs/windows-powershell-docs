---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
Module Name: MSMQ
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/msmq/new-msmqqueue?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-MsmqQueue
---

# New-MsmqQueue

## SYNOPSIS
Creates public or private queues.

## SYNTAX

```
New-MsmqQueue [-Name] <String[]> [-QueueType <MSMQQueueType>] [-Transactional] [-Label <String>]
 [-Authenticate] [-Journaling] [-QueueQuota <Int64>] [-JournalQuota <Int64>]
 [-PrivacyLevel <EncryptionRequired>] [-MulticastAddress <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-MsmqQueue** cmdlet creates public or private queues.
The cmdlet returns **System.Messaging.MessageQueue** objects that represent the new queues.
If you do not specify *QueueType* parameter, the cmdlet creates a private queue.

## EXAMPLES

### Example 1: Create a public queue
```
PS C:\> New-MsmqQueue -Name "OrderQueue" -QueueType Public
```

This command creates a public queue named OrderStatus.

### Example 2: Create a private queue for authenticated messages
```
PS C:\> New-MsmqQueue -Name "OrderQueue" -Authenticate -MulticastAddress "234.12.3:8001" -QueueQuota 200000
```

This command creates a private queue named OrderQueue.
The queue accepts only authenticated messages.
The command specifies a quota size for the queue.

## PARAMETERS

### -Authenticate
Indicates that the queue accepts only authenticated messages.

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

### -JournalQuota
Specifies the maximum size of the journal queue.
Specify a value in kilobytes.
If you do not specify a value, this cmdlet uses the default journal queue quota.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Journaling
Indicates that received messages are copied to the journal queue.

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
The label that this parameter specifies describes the queue.
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

### -MulticastAddress
Specifies the multicast address associated with the queue.
If you do not specify a multicast address, the cmdlet does not assign a multicast address to this queue.

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

### -Name
Specifies an array of names of queues.
This parameter specifies friendly names of queues.
This parameter does not support wildcard characters.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PrivacyLevel
Specifies the privacy level associated with the queue.
The default value is Optional.

```yaml
Type: EncryptionRequired
Parameter Sets: (All)
Aliases:
Accepted values: None, Optional, Body

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -QueueQuota
Specifies the maximum size, in kilobytes, of the queue.
If you do not specify a value, this cmdlet uses the default queue quota.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -QueueType
Specifies a queue type.
The acceptable values for this parameter are:

- Private.
The cmdlet creates a private queue with the name that the *Name* parameter specifies.
- Public.
The cmdlet creates a public queue with the name that the *Name* parameter specifies.

The default value is Private.

```yaml
Type: MSMQQueueType
Parameter Sets: (All)
Aliases:
Accepted values: Private, Public

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Transactional
Indicates that the cmdlet creates a transactional queue at the specified path.

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

### System.String[]

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Clear-MsmqQueue](./Clear-MSMQQueue.md)

[Get-MsmqQueue](./Get-MsmqQueue.md)

[Receive-MsmqQueue](./Receive-MsmqQueue.md)

[Remove-MsmqQueue](./Remove-MsmqQueue.md)

[Send-MsmqQueue](./Send-MsmqQueue.md)

[Set-MsmqQueue](./Set-MsmqQueue.md)

