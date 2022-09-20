---
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
Module Name: MSMQ
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/msmq/get-msmqqueue?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-MsmqQueue
---

# Get-MsmqQueue

## SYNOPSIS
Gets message queues.

## SYNTAX

### All (Default)
```
Get-MsmqQueue [[-Name] <String[]>] [-QueueType <QueueType>] [<CommonParameters>]
```

### Journal
```
Get-MsmqQueue [[-Name] <String[]>] [-QueueType <QueueType>] [-Journal] [<CommonParameters>]
```

### SubQueue
```
Get-MsmqQueue [[-Name] <String[]>] [-QueueType <QueueType>] [-SubQueue <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-MsmqQueue** cmdlet gets an array of **MsmqQueue** objects.
Each **MsmqQueue** object represents an existing private, public, or system queue.
This cmdlet gets queues that are local to the computer where you run the cmdlet.
If you do not specify parameters, this cmdlet gets all public, private, and system queues of the host computer.

## EXAMPLES

### Example 1
```
PS C:\> Get-MsmqQueue
```

### Example 2
```
PS C:\>Get-MsmqQueue -Name "Order*" -QueueType Private
```

### Example 3
```
PS C:\>Get-MsmqQueue -Name "Order*" -Journal -QueueType Private
```

### Example 4
```
PS C:\>Get-MsmqQueue -QueueType SystemJournal
```

## PARAMETERS

### -Journal
Indicates that this cmdlet retrieves the Journal queue or queues that match the **Name** parameter.

```yaml
Type: SwitchParameter
Parameter Sets: Journal
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies an array of names of queues.
This cmdlet accepts wildcard characters.
The default value is *.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -QueueType
Specifies a queue type.
The acceptable values for this parameter are:

- PrivateAndPublic.
The cmdlet gets public and private queues that match the **Name** parameter. 
- Private.
The cmdlet gets private queues that match the **Name** parameter. 
- Public.
The cmdlet gets public queues that match the **Name** parameter. 
- SystemDeadLetter.
The cmdlet gets non-transactional dead-letter queues that match the **Name** parameter. 
- SystemJournal.
The cmdlet gets system journal queues that match the **Name** parameter. 
- SystemTransactionalDeadLetter.
The cmdlet gets transactional dead-letter queues that match the **Name** parameter. 

The default value is PrivateAndPublic.

```yaml
Type: QueueType
Parameter Sets: (All)
Aliases: 
Accepted values: PrivateAndPublic, Private, Public, SystemJournal, SystemDeadLetter, SystemTransactionalDeadLetter

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubQueue
Specifies a subqueue object to get for the main queue.
If the subqueue does not exist, the cmdlet creates it implicitly.
The question mark (?) and asterisk (*) are not interpreted as wildcard characters, but part of the subqueue name.

```yaml
Type: String
Parameter Sets: SubQueue
Aliases: 

Required: False
Position: Named
Default value: None
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

[New-MsmqQueue](./New-MsmqQueue.md)

[Receive-MsmqQueue](./Receive-MsmqQueue.md)

[Remove-MsmqQueue](./Remove-MsmqQueue.md)

[Send-MsmqQueue](./Send-MsmqQueue.md)

[Set-MsmqQueue](./Set-MsmqQueue.md)

