---
author: Kateyanne
external help file: MSMQ_Cmdlets.xml
manager: dansimp
Module Name: MSMQ
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/msmq/new-msmqqueue?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-MsmqQueue

## SYNOPSIS
Creates a MSMQ queue.

## SYNTAX

```
New-MsmqQueue [-Name] <String[]> [-Authenticate] [-Journaling] [-JournalQuota <Int64>] [-Label <String>]
 [-MulticastAddress <String>] [-PrivacyLevel] [-QueueQuota <Int64>] [-QueueType] [-Transactional]
```

## DESCRIPTION
The **New-MsmqQueue** cmdlet will create new public or private queues with the properties passed as parameters.
The cmdlet returns **System.Messaging.MessageQueue** objects that represent the created queues.
If the queue type parameter is not explicitly provided, the cmdlet defaults to a private queue.

## EXAMPLES

### Example 1: Create a public MsmqQueue
```
PS C:\>New-MsmqQueue -Name "OrderQueue" -QueueType Public
```

This command creates a public MsmqQueue named OrderQueue.

### Example 2: Create a private MsmqQueue with a quota and multicast address
```
PS C:\>New-MsmqQueue -Name "OrderQueue" -Authenticate True -QueueQuota 200000 -MulticastAddress "234.12.3:8001"
```

This command creates a private MsmqQueue named OrderQueue that has a quota of 200000 and a specific multicast address.

## PARAMETERS

### -Authenticate
Indicates that this cmdlet accepts authenticated messages for the queue.

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

### -Journaling
Indicates that this cmdlet copies received messages to the journal queue.

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
Specifies the maximum size of the journal queue in KB.
If you do not specify a value the default journal queue quota is used.

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

### -Label
Specifies the queue description.

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
If you do not specify a value no multicast address is assigned to this queue.

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
Specifies an array that this cmdlet assigns the name of a queue.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByValue)
Accept wildcard characters: False
```

### -PrivacyLevel
Specifies the privacy level associated with the queue.

```yaml
Type: SwitchParameter
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
Specifies the maximum size of the queue in kilobytes (KB).
If you do not specify a value this cmdlet uses the default queue quote.

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
Specifies the type of queue this cmdlet creates.
If you specify the value as Private, this cmdlet creates a private queue with the queue name as specified by the **Name** parameter.
If you specify the value as Public, this cmdlet creates a public queue with the queue name as specified by the **Name** parameter.

```yaml
Type: SwitchParameter
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
Indicates that this cmdlet creates a transactional queue at the specified path.

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

[Receive-MsmqQueue](./Receive-MsmqQueue.md)

[Remove-MsmqQueue](./Remove-MsmqQueue.md)

[Send-MsmqQueue](./Send-MsmqQueue.md)

[Set-MsmqQueue](./Set-MsmqQueue.md)

