---
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
Module Name: MSMQ
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/msmq/set-msmqqueue?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-MsmqQueue
---

# Set-MsmqQueue

## SYNOPSIS
Sets properties of queues.

## SYNTAX

```
Set-MsmqQueue -InputObject <MessageQueue[]> [-Label <String>] [-Authenticate <Boolean>] [-Journaling <Boolean>]
 [-QueueQuota <Int64>] [-JournalQuota <Int64>] [-PrivacyLevel <EncryptionRequired>]
 [-MulticastAddress <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-MsmqQueue** cmdlet sets properties of queues.
This cmdlet returns an **MsmqQueue** object that represents the modified queue.
Specify private or public queues to modify.
If you specify a journal queue, system journal queue, system dead-letter queue, or system transactional dead-letter queue, the cmdlet returns an error.

## EXAMPLES

### Example 1
```
PS C:\>Get-MsmqQueue -Name "order*" -QueueType Private | Set-MsmqQueue -Journaling -QueueQuota 500000
```

## PARAMETERS

### -Authenticate
Indicates whether the queue accepts only authenticated messages.
There is no default value.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies an array of **MsmqQueue** objects.
This cmdlet modifies properties of the queues that this parameter specifies.
This parameter accepts pipeline input.

```yaml
Type: MessageQueue[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JournalQuota
Specifies the maximum size of the journal queue.
Specify a value in kilobytes.
There is no default value.

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
Indicates whether to copy received messages to the journal queue.
There is no default value.

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

### -Label
Specifies a label.
The label that this parameter specifies describes the queue.
There is no default value.

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
There is no default value.

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
There is no default value.

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
There is no default value.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Clear-MsmqQueue](./Clear-MSMQQueue.md)

[Get-MsmqQueue](./Get-MsmqQueue.md)

[New-MsmqQueue](./New-MsmqQueue.md)

[Receive-MsmqQueue](./Receive-MsmqQueue.md)

[Remove-MsmqQueue](./Remove-MsmqQueue.md)

[Send-MsmqQueue](./Send-MsmqQueue.md)

