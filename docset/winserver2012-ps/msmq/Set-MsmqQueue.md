---
external help file: MSMQ_Cmdlets.xml
Module Name: MSMQ
online version: https://docs.microsoft.com/powershell/module/msmq/set-msmqqueue?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-MsmqQueue

## SYNOPSIS
Sets queue properties.

## SYNTAX

```
Set-MsmqQueue [-Authenticate <Boolean>] [-Journaling <Boolean>] [-JournalQuota <Int64>] [-Label <String>]
 [-MulticastAddress <String>] [-PrivacyLevel <EncryptionRequired>] [-QueueQuota <Int64>]
 -InputObject <MessageQueue[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-MsmqQueue** cmdlet sets the properties of the private and public queues that are represented by the supplied **MsmqQueue** objects.
This cmdlet will return an error when supplied with a journal queue, system journal queue, system dead-letter queue, or a system transactional dead-letter queue.
This cmdlet returns an **MsmqQueue** object that represents the modified queue.

## EXAMPLES

### Example 1: Set the properties of a specified queue
```
PS C:\>Get-MsmqQueue -Name "Order*" -QueueType Private | Set-MsmqQueue -QueueQuota 500000 -Journaling
```

This command sets the queue quota to 500000 on all queues that have the   wildcard named Order*.

## PARAMETERS

### -Authenticate
Indicates whether this cmdlet accepts only authenticated messages from the queue.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies an array of **MsmqQueue** objects that represents a queue on which the properties are to be set.
This parameter accepts pipelined input.

```yaml
Type: MessageQueue[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByValue)
Accept wildcard characters: False
```

### -Journaling
Indicates whether this cmdlet copies received messages to the journal queue.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JournalQuota
Specifies the maximum size of the journal queue in kilobytes (KB).

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
Specifies the queue description that this cmdlet modifies for the queue.

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

### -PrivacyLevel
Specifies the privacy level associated with the queue.

```yaml
Type: EncryptionRequired
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -QueueQuota
Specifies the maximum size of the queue in kilobytes.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
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

[Send-MsmqQueue](./Send-MsmqQueue.md)

